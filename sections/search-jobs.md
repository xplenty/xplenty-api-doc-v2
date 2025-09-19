## Search Jobs

### Description
Search engine was optimized to find the best match using intuitive syntax. Results are ordered by relevance by default, so you can easily compare all returned records and choose the best one.
Format of the query string is the following:
`attribute1:value1 attribute2:"some terms with spaces" date_attribute1:>2016-01-01 date_attribute2:<2016-01-02 -attribute2:value3 other text`
Here are a few important rules:

1. For comparable attributes like integer or date, you can use the following operators:
  * `:` - equal
  * `:>` - greater than or equal
  * `:<` - less than or equal
2. Negation is represented by `-` sign at the beginning of the attribute like: `-name:John`. It means we do not want to have results where value of the `name` attribute contains `John` phrase.
3. Negation cannot be used for comparable types like integer or date.
3. When an attribute with the same sign is used twice in a search query - the two instances are implicitly joined with OR, in case of different sign, phrases are implicitly joined with AND.
4. Two different attributes are implicitly joined with AND.

Possible attributes:

* **id**
* **started** - the date and time the job started running in ISO8601.
* **finished** - the date and time the job finished running in ISO8601.
* **status**
* **duration**
* **package** - search in related packages by the **name** and **id** attributes
* **log** - search in related logs by the **body** attribute
* **schedule** - search in related schedule names by the **name** attribute
* **user** - search in related users (owners) by the **name** and **email** attributes

Free text (not assigned to any attribute) will search in job ID and package name. They will be joined with OR.

Please read the document describing [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md) for other details.


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
q|Y| |Terms, e.g. `status:pending test package`
sort|N|"relevance"|Possible values are `id`, updated`, `created` or `relevance`. Jobs list will be sorted by the jobs' requested attribute or relevance if no sort parameter is specified, or specified parameter is wrong.
direction|N|"asc"|Possible values are: `asc`, `desc`. Jobs will be sorted in ascending or descending order of the `sort` attribute.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/search" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "q":"status:pending test package",
    "sort":"created",
    "direction":"desc"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 304,
    "status": "failed",
    "variables":
    {
        "InputPath": "'/today'"
    },
    "owner_id": 1,
    "progress": 0,
    "attempts": 1,
    "master_auto_retry_attempts": 3,
    "outputs_count": 0,
    "outputs": [],
    "started_at": "2013-03-04T08:02:20Z",
    "created_at": "2013-03-04T08:02:17Z",
    "updated_at": "2013-03-04T08:03:01Z",
    "failed_at": null,
    "cluster_id": 176,
    "package_id": 103,
    "errors": "Package failed to execute.",
    "runtime_in_seconds": 40,
    "completed_at": "2013-03-04T08:03:01Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/304",
    "html_url": "https://xplenty.com/xplenation/jobs/304",
    "log_url": "https://api.xplenty.com/xplenation/api/jobs/304/log",
    "creator":
    {
        "type":"Schedule",
        "id":1,
        "display_name": "Schedule 1",
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    }
  },
  {
    "id": 303,
    "status": "failed",
    "variables": {},
    "owner_id": 1,
    "progress": 0,
    "attempts": 2,
    "master_auto_retry_attempts": 3,
    "outputs_count": 0,
    "outputs": [],
    "started_at": "2013-03-04T07:38:33Z",
    "created_at": "2013-03-04T07:38:27Z",
    "updated_at": "2013-03-04T07:39:11Z",
    "failed_at": null,
    "cluster_id": 176,
    "package_id": 434,
    "errors": "Package failed to execute.",
    "runtime_in_seconds": 38,
    "completed_at": "2013-03-04T07:39:11Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/303",
    "html_url": "https://xplenty.com/xplenation/jobs/303",
    "log_url": "https://api.xplenty.com/xplenation/api/jobs/303/log",
    "creator":
    {
        "type":"Schedule",
        "id":1,
        "display_name": "Schedule 1",
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    }
  },
  {
    "id": 299,
    "status": "stopped",
    "variables": {},
    "owner_id": 1,
    "progress": 0,
    "attempts": 0,
    "master_auto_retry_attempts": null,
    "outputs_count": 0,
    "outputs": [],
    "started_at": null,
    "created_at": "2013-03-04T06:58:48Z",
    "updated_at": "2013-03-04T07:17:51Z",
    "failed_at": null,
    "cluster_id": 176,
    "package_id": 434,
    "errors": "Package failed to execute.",
    "runtime_in_seconds": 0,
    "completed_at": "2013-03-04T07:17:51Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/299",
    "html_url": "https://xplenty.com/xplenation/jobs/299",
    "log_url": "https://api.xplenty.com/xplenation/api/jobs/299/log",
    "creator":
    {
        "type":"User",
        "id":1,
        "display_name": "Schedule 1",
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    }
  },
  {
    "id": 157,
    "status": "completed",
    "variables": {},
    "owner_id": 1,
    "progress": 1,
    "attempts": 4,
    "master_auto_retry_attempts": 4,
    "outputs_count": 2,
    "outputs": [
      {
        "component": {
          "name": "destination7",
          "type": "cloud_storage_destination_component",
          "fields": [
            "id",
            "account_name"
          ]
        },
        "created_at": "2013-03-04T07:17:51Z",
        "id": 521,
        "name": "projected_results",
        "preview_url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521/preview",
        "records_count": 10415234,
        "updated_at": "2013-03-04T07:17:51Z",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521"
      },
      {
        "component": {
          "name": "destination7",
          "type": "cloud_storage_destination_component",
          "fields": [
            "id",
            "account_name"
          ]
        },
        "created_at": "2013-03-04T07:14:44Z",
        "id": 522,
        "name": "projected_results2",
        "preview_url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522/preview",
        "records_count": 423,
        "updated_at": "2013-03-04T07:14:44Z",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522"
      }
    ],
    "started_at": "2012-12-30T14:21:29Z",
    "created_at": "2012-12-30T14:21:18Z",
    "updated_at": "2012-12-30T14:29:29Z",
    "cluster_id": 52,
    "package_id": 434,
    "errors": "",
    "runtime_in_seconds": 417,
    "completed_at": "2012-12-30T14:29:29Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/157",
    "html_url": "https://xplenty.com/xplenation/jobs/157",
    "log_url": "https://api.xplenty.com/xplenation/api/jobs/157/log",
    "creator":
    {
        "type":"Schedule",
        "id":2,
        "display_name": "Schedule 2",
        "url": "https://api.xplenty.com/xplenation/api/schedules/2",
        "html_url": "https://xplenty.com/xplenation/schedules/2"
    }
  }
]
```
