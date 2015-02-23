## List User's Accounts 

### Description
This call returns information for a list of active accounts in which the authenticated user is a member (with either admin or  member role). Optionally, you can supply the input parameters to filter the account list so that it contains only
accounts with a specific role or id, and to determine the order by which the list will be sorted.

The details returned for each account are:

* **id** - the account's numeric identifier
* **name** - the name given to the account upon creation
* **region** - the account's region
* **location** - the account's location
* **billing_email** - the account's billing email
* **gravatar_email** - the account's gravatar email
* **avatar_url** - the url for the account's avatar
* **created_at** - the date and time the account was created
* **updated_at** - the date and time the account was last updated
* **schedules_count** - the number of schedules for the account
* **connections_count** - the number of connections for the account
* **role** - the member's role in the account ("admin" or "member")
* **owner** - indicator if the member is the account owner
* **members_count** - the number of members in the account
* **packages_count** - the number of packages for the account
* **jobs_count** - the number of jobs for the account
* **running_jobs_count** - the number of running jobs for the account

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
role|N|"all"|Possible values: ```admin```, ```member```, ```all```. The call will return only accounts where the authenticated user has the given role, or all the accounts if the value is not specified or the 'all' value is specified.
sort|N|"created"|Possible values are  ```updated```, ```created```, ```id```, ```name```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The accounts will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The account list will only contain accounts updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/accounts?role=<roleFilter>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id":"xplenty-admin",
    "name":"Xplenty Admin",
    "region":"amazon-web-services::us-east-1",
    "location":null,
    "billing_email":"admin@xplenty.com",
    "gravatar_email":"admin@xplenty.com",
    "avatar_url":"http://gravatar.com/avatar/d41d8cd98f00b204e9800998ecf8427e.png?d=retro&s=140",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z",
    "schedules_count":0,
    "connections_count":2,
    "role":"admin",
    "owner":true,
    "members_count":2,
    "packages_count":0,
    "jobs_count":0,
    "running_jobs_count":0
  },
  {
    "id":"sample-admin",
    "name":"Sample Admin",
    "region":"amazon-web-services::us-east-1",
    "location":null,
    "billing_email":"admin@example.com",
    "gravatar_email":"admin@example.com",
    "avatar_url":"http://gravatar.com/avatar/d24d8cd923f00b204e9800998ecf8427e.png?d=retro&s=140",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z",
    "schedules_count":0,
    "connections_count":2,
    "role":"member",
    "owner":false,
    "members_count":3,
    "packages_count":0,
    "jobs_count":1,
    "running_jobs_count":0
  }
]
```
