# Xplenty API Specification

## Introduction

The Xplenty API provides functions for controlling and monitoring Xplenty clusters and jobs.
After defining an Xplenty data processing package using the Xplenty web application, you can call the Xplenty API to:
* create clusters
* run jobs
* monitor their progress
* terminate jobs and clusters

You can choose to use the [Xplenty REST API](#RESTSpec), or one of its wrapper [Libraries](#Libraries).

These are the topics covered on this page:
* [Getting Started](#GettingStarted)
* [Xplenty Terminology](#XplentyTerminology)
* [REST Interface Specifications](#RESTSpec)
* [Libraries](#Libraries)
* [Security](#Security)
* [Collection Resources and Pagination](#Collection)
* [Rate Limits](#RateLimits)
* [API Resources](#ApiResources)
* [Terms of Service](#ToS)
* [References](#References)

<a id="GettingStarted" name="GettingStarted">
## Getting Started
</a>

For a quick overview of how to get started with the Xplenty REST API, you can read:
* [Xplenty Control and Monitoring Tasks](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/xplenty-control-and-monitoring-tasks.md)
* [Xplenty Typical Workflow](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/xplenty-typical-workflow.md)

<a id="XplentyTerminology" name="XplentyTerminology">
## Xplenty Terminology
</a>

These are some of the terms you will encounter in the Xplenty API documentation.

### Package

An Xplenty **package** is a data flow definition that you define in the Xplenty web application.
It describes the data to process (location, schema, fields), data manipulation to perform, and the output destinations (location, schema). The package's workflow is implemented by jobs.

### Job
An Xplenty **job** is a process that is responsible for performing a data flow according to a specific package on a cluster. The job is a batch process that runs on a finite amount of data and then terminates. Several jobs can run the same package simultaneously.
When you call the Xplenty API to run a new job, you supply the name of the package whose workflow the job should perform, and the cluster on which to run.

### Cluster

An Xplenty **cluster** is a group of machines (nodes) that is allocated exclusively to your account's users. You can create one or more clusters, and you can run one or more jobs on each cluster. A cluster that you've created remains allocated to your account until you request to terminate the cluster.

### Schedule

An Xplenty **schedule** executes packages periodically starting at a specified date and time. The packages will be executed as scheduled, using an existing cluster that fits the scheduled cluster size or if one doesn't exist, a cluster will be provisioned automatically with the number of specified nodes. By default, the cluster is taken down as soon as package execution is completed.

### Delivery

An Xplenty **delivery** is a blueprint for a set of resources which automates the task of delivering data from one place to another.

### Account and User
An Xplenty **account** represents a related group (usually a company) of Xplenty **users**.
An account is created when the user signs up to use the Xplenty service. An API key is generated for the user, which must be supplied when calling the Xplenty API.

<a id="RESTSpec" name="RESTSpec">
## REST Interface Specifications
</a>

### Using the Xplenty REST API

The Xplenty REST API conforms to the design principles of [Representational State Transfer (REST)](http://en.wikipedia.org/wiki/Representational_State_Transfer).

To get a quick start with the Xplenty API, we recommend using the [curl](http://curl.haxx.se) command-line utility.

All URLs start with:
    https://api.xplenty.com/{account_id}/api/

Parameter values should be converted to UTF-8 and [URL encoded](http://en.wikipedia.org/wiki/Percent_encoding).

All Xplenty APIs support jsonp, which is the json format with a callback specified, such as:

    callback=callback_method

All date parameters will be treated as UTC and their formats must be in ISO 8601 format:

    YYYY-MM-DDTHH:MM:SSZ

All published date and time objects are UTC based and returned in ISO 8601 format:

    YYYY-MM-DDTHH:MM:SSZ

### Mime Types

The API presently supports the [JSON](http://en.wikipedia.org/wiki/Json) format only.
Specify a custom mime type in the [Accept] header as follows:

    application/vnd.xplenty+json

Unless you specify a version, the latest representation of resources will always be returned in the response. If you’re building an application and want to ensure a consistent response format, specify a version as follows:

    application/vnd.xplenty+json; version=2

### Parameters

Many API methods take optional parameters. For GET requests, any parameters not specified as a segment in the path can be passed as an HTTP query string parameter:

```shell
$ curl -i "https://api.xplenty.com/xplenty-account/api/clusters?status=available"
In this example, the 'xplenty-account' value is provided for the :account_id parameter in the path while the 'available' value is provided for :status that is passed in the query string.
```

For POST, PATCH, PUT, and DELETE requests, parameters not included in the URL should be JSON encoded:

```shell
$ curl -X POST -u api_key "https://api.xplenty.com/xplenty-account/api/clusters" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "my cluster",
    "description": "production cluster",
    "type": "production",
    "nodes": 2
  }'
```

### CORS (Cross Origin Resource Sharing)

The Xplenty API supports Cross Origin Resource Sharing.

You can read the [CORS W3C working draft](http://www.w3.org/TR/cors), or [this introduction](http://www.w3.org/TR/cors) from the HTML 5 Security Guide.

The latest version of the Xplenty API (V1) supports CORS requests from any domain.

### Response Codes and Error Messages

**HTTP Status Codes**

These are the HTTP status codes that the Xplenty API can return:

* **200 OK**: Request succeeded.
* **201 Created**: The requested resource was created successfully.
* **204 No Content**: Request succeeded. No content is returned.
* **304 Not Modified**: There was no new data to return.
* **400 Bad Request**: The request was invalid.  An accompanying error message will explain why.
* **401 Unauthorized**: You are attempting to access the API with invalid credentials.
* **402 Payment Required**: You must confirm your billing info to use this API.
* **403 Forbidden**: The request has been refused.  An accompanying error message will explain why.
* **404 Not Found**: The URI requested is invalid or the resource requested does not exist.
* **406 Not Acceptable**: The requested mime-type is not acceptable.
* **415 Unsupported Media Type**: The specified media type is not supported.
* **422 Unprocessable Entity**: You have sent invalid fields.
* **429 Too Many Requests**: The request exceeded the rate limitations.
* **500 Internal Server Error**: An internal error occurred in the request.
* **502 Bad Gateway**: Xplenty is down or being upgraded.
* **503 Service Unavailable**: The Xplenty servers are up, but overloaded with requests. Try again later.

**Error Responses**

When the API returns an error message, it does so in your requested format. For example, an error from a JSON method might look like this:

```json
{
    "message": "Item not found."
}
```

<a id="#Libraries" name="Libraries">
## Libraries
</a>

Use a wrapper in the official Xplenty library, or a [third party library](#Thirdparty).

[Java wrapper](https://github.com/xplenty/xplenty.jar)
[Python wrapper](https://github.com/xplenty/xplenty.py)
[Ruby wrapper](https://github.com/xplenty/xplenty.rb)

<a id="Thirdparty" name="Thirdparty">
### Third Party
[.NET wrapper for Xplenty Rest API](https://github.com/dilievsky/xplenty.dll)
</a>

<a id="Security" name="Security">
## Security
</a>

### Encrypted Communication (SSL)

Xplenty provides all REST API methods over SSL. Whenever your code might be operating on a non-secure network (that is, if you're developing a client application), please make use of SSL for all authenticated or sensitive requests. For example, requesting cluster information should be performed by an Xplenty client over SSL. Service-to-service communication may not benefit from SSL if you trust your hosting provider (or if you are your own hosting provider).

### Authentication
Most of the Xplenty API calls require authentication, supplied in the form of the API key which is generated for each account.

In order to get your API key, view your user's personal information page. See [here](http://community.xplenty.com/knowledgebase/articles/178926) for more information.

Once you have an API key, you can either attach it to each request as a "key" parameter, or use HTTP Basic Authentication with the API key as a username and a blank password. Here's an example using curl (the colon separates the username and password):

```shell
curl -H "Accept: application/vnd.xplenty+json" -u <apikeyhere>: https://api.xplenty.com/:account_id/clusters
```
API key authentication works well for personal scripts, but is not recommended for third party services. We plan to deliver OAuth in the near future to provide better granularity and control when providing access to third party services.

<a id="Collection" name="Collection">
## Collection Resources and Pagination
</a>

The response to a GET request for collection resources (e.g. clusters) may not return all the objects in the collection, depending on the number of objects. To query collection resources incrementally, use the following parameters:

* **offset** - the index of the first object to retrieve, starting from 0
* **limit** - the number of items to return (default is 20, maximum is 100)

Information about pagination is provided in [the Link header](http://tools.ietf.org/html/rfc5988) of an API call, so that you know how many more requests are needed to retrieve the complete list of collection resources:

```shell
$ curl -I "https://api.xplenty.com/:account_id/api/clusters?offset=3&limit=10"
```

The `-I` parameter indicates that we only care about the headers, not the actual content.

In examining the result, you'll notice some information in the Link header that looks like this:

```
Link: <https://api.xplenty.com/:account_id/api/clusters?offset=4&limit=10>; rel="next", 
      <https://api.xplenty.com/:account_id/api/clusters?offset=2&limit=10>; rel="prev"
```

`rel="next"` says that the next offset is `offset=4` and `rel="prev"` says that the previous offset is `offset=2`. Using this information, you could traverse through the list of results in the API call.

<a id="RateLimits" name="RateLimits">
## Rate Limits
</a>

The Xplenty API only allows clients to make a limited number of calls in a given hour. It uses a credit allocation system to ensure fair distribution of capacity. Each user is allocated 5,000 credits per hour. This is keyed off either your login or the request IP. If you exceed this limit, you'll get a "429 Too Many Requests" response for subsequent requests.

All Xplenty API methods are rate-limited except for querying the rate limit.
You can check your rate limit status without incurring an API hit, as follows:

    `GET /rate_limit_status`

Every time you call the API, the current rate status will be returned in the response under the following headers:

<table>
<tr><td><b>HTTP Header</b></td><td><b>Description</b></td></tr>
<tr><td>X-RateLimit-Limit</td><td>Total credits allocated</td></tr>
<tr><td>X-RateLimit-Remaining</td><td>Total credits available</td></tr>
</table>

### Cost of API calls
Unless otherwise noted, an API call deducts 1 credit from your allocation.


When a client exceeds the allocated rate limit, the Xplenty API returns a "429 Too Many Requests" response with an associated "Rate Limit Exceeded" message as the error description.

### Whitelisting
Xplenty REST API whitelisting is not supported.

### Blacklisting
We ask that you honor the rate limit. If your application abuses the rate limit your user will be blacklisted, and you will be unable to get a response from the Xplenty API.

If your user has been blacklisted and you think there has been an error, you can contact the email address on the API support page. So we can get you back online quickly, please include the following information:

1. If you are using the REST API, make a call to the /rate_limit_status from the computer which is blacklisted and include the response in your email.
2. Explain why you think your application was blacklisted.
3. Describe in detail how you have fixed the problem that you think caused you to be blacklisted.

<a id="ApiResources" name="ApiResources">
## API Resources
</a>

### Xplenty API Methods

These are the methods supported by the Xplenty API:

* [Create Cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-cluster.md)
* [List Clusters](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-clusters.md)
* [Search Clusters](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/search-clusters.md)
* [Update Cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-cluster.md)
* [Get Cluster Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-cluster-information.md)
* [Terminate Cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/terminate-cluster.md)
* [Run Job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/run-job.md)
* [List Jobs](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-jobs.md)
* [List Job Children](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-job-children.md)
* [Search Jobs](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/search-jobs.md)
* [Get Job Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-information.md)
* [Terminate Job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/terminate-job.md)
* [Watch Clusters and jobs](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/watch-clusters-and-jobs.md)
* [Get Job Execution Variables](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-execution-variables.md)
* [List Packages](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-packages.md)
* [Search Packages](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/search-packages.md)
* [Update Package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-package.md)
* [Run Package Validation](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/run-package-validation.md)
* [Get Package Validation Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-package-validation-information.md)
* [List Package Validation](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-package-validations.md)
* [Create Package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-package.md)
* [Create Schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-schedule.md)
* [Get Package Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-package-information.md)
* [Delete Package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/delete-package.md)
* [List Schedules](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-schedules.md)
* [Search Schedules](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/search-schedules.md)
* [Update Schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-schedule.md)
* [Get Schedule Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-schedule-information.md)
* [Delete Schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/delete-schedule.md)
* [Watch Schedules](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/watch-schedules.md)
* [Run Schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/run-schedule.md)
* [Get Account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-account.md)
* [Create Account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-account.md)
* [List Accounts](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-accounts.md)
* [Update Account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-account.md)
* [Delete Account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/delete-account.md)
* [Get Account Payment Method](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-payment-method.md)
* [Add Account Member](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/add-member.md)
* [Get Account Member Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-member-information.md)
* [List Account Members](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-members.md)
* [Delete Account Member](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/delete-member.md)
* [List Connection Types](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-connection-types.md)
* [List Account Connections](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-connections.md)
* [Create Account Connections](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-connection.md)
* [Test New Account Connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/test-new-connection.md)
* [Update Account Connections](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-connection.md)
* [Get Account Connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-connection-information.md)
* [Delete Account Connections](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/delete-connection.md)
* [Test Connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/test-connection.md)
* [Validate Connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/validate-connection.md)
* [Import Connection schema](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/import-connection-schema.md)
* [List Bing Ads Accounts](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-bingads-accounts.md)
* [List Bing Ads Columns](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-bingads-columns.md)
* [List Salesforce Objects](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-salesforce-objects.md)
* [List Salesforce Fields](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-salesforce-fields.md)
* [List Facebook Ads Insights Accounts](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-facebook-ads-insights-accounts.md)
* [List Facebook Ads Insights Fields](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-facebook-ads-insights-fields.md)
* [List Google Analytics Accounts](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-google-analytics-accounts.md)
* [List User Notifications](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-notifications.md)
* [Mark User Notifications as read](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/mark-notifications.md)
* [Get Authenticated User Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-authenticated-user-information.md)
* [Regenerate Authenticated User Tokens](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/regenerate-authenticated-user-tokens.md)
* [Update Authenticated User](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-authenticated-user.md)
* [Create Public Key](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-public-key.md)
* [List User Public Keys](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-public-keys.md)
* [Delete User Public Key](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/delete-public-key.md)
* [Get User Public Key Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-public-key-information.md)
* [List User Notifications](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-notifications.md)
* [Mark User Notifications as read](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/mark-notifications.md)
* [Reset User Password](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/reset-user-password.md)
* [List Supported Stacks](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-stacks.md)
* [List Available Regions](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-regions.md)
* [List Available Account Regions](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-account-regions.md)
* [List System Variables](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-system-variables.md)
* [List Product Updates](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-product-updates.md)
* [List Hook Types](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-hook-types.md)
* [List Hooks](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-hooks.md)
* [Search Hooks](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/search-hooks.md)
* [Get Hook Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-hook-information.md)
* [Create Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-hook.md)
* [Update Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-hook.md)
* [Ping Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/ping-hook.md)
* [Reset Hook Salt](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/reset-hook-salt.md)
* [Delete Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/delete-hook.md)
* [List Supported Time Zones](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-timezones.md)
* [List Invoices](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-invoices.md)
* [Get Invoice Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-invoice-information.md)
* [Help](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/help.md)
* [List Deliveries](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-deliveries.md)
* [Get Delivery Information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-delivery-information.md)
* [Create Delivery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-delivery.md)
* [Delete Delivery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/delete-delivery.md)

## Terms of Service

Please refer to our [Terms of Service](http://www.xplenty.com/tos) page.

## References

[Representational State Transfer (REST)](http://en.wikipedia.org/wiki/Representational_State_Transfer)

[Secure Socket Layer (SSL)](http://en.wikipedia.org/wiki/Secure_Sockets_Layer)
