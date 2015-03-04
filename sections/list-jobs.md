## List Jobs

### Description
This call returns information for the list of [jobs](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md) that were created by users in your account.
You can use this information to monitor your jobs and their status.
Optionally, you can supply the input parameters to filter the job list so that it contains only jobs with a specific status, and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
status|N|"all"|Possible values are any status listed above or ```all```. The call will return only jobs with the given status, or all the clusters if the "all" value is specified.
sort|N|"created"|Possible values are ```updated``` or ```created```. The job list will be sorted by the jobs' "updated_at" or "created_at" value respectively.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The jobss will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The job list will only contain jobs updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
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
    "url": "https://api.xplenty.com/xplenation/api/jobs/304"
  },
  {
    "id": 303,
    "status": "failed",
    "variables": {},
    "owner_id": 1,
    "progress": 0,
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
    "url": "https://api.xplenty.com/xplenation/api/jobs/303"
  },
  {
    "id": 299,
    "status": "stopped",
    "variables": {},
    "owner_id": 1,
    "progress": 0,
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
    "url": "https://api.xplenty.com/xplenation/api/jobs/299"
  },
  {
    "id": 157,
    "status": "completed",
    "variables": {},
    "owner_id": 1,
    "progress": 1,
    "outputs_count": 2,
    "outputs": [
      {
        "component_name": "destination1",
        "created_at": "2013-03-04T07:17:51Z",
        "id": 521,
        "name": "projected_results",
        "preview_url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521/preview",
        "records_count": 10415234,
        "updated_at": "2013-03-04T07:17:51Z",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521"
      },
      {
        "component_name": "destination2",
        "created_at": "2013-03-04T07:14:44Z",
        "id": 522,
        "name": "projected_results2",
        "preview_url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522/preview",
        "records_count": 423,
        "updated_at": "2013-03-04T07:14:44Z",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522"
      },
    ],
    "started_at": "2012-12-30T14:21:29Z",
    "created_at": "2012-12-30T14:21:18Z",
    "updated_at": "2012-12-30T14:29:29Z",
    "cluster_id": 52,
    "package_id": 434,
    "errors": "",
    "runtime_in_seconds": 417,
    "completed_at": "2012-12-30T14:29:29Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/157"
  }
]
```
