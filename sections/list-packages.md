## List Packages

### Description
List [packages](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md) that are accessible by authenticated user.
You can use this information to monitor your packages.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
flow_type|N|"all"|Possible values are `workflow`, `dataflow`, `all`. The call will return only packages with the given flow_type, or all the packages if the "all" value is specified.
sort|N|"created"|Possible values are `updated`, `created` or `name`. The packages list will be sorted by the packages' `updated_at`, `created_at` or `name` value respectively.
direction|N|"desc"|Possible values are: `asc`, `desc`. The packages will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The packages list will only contain packages updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/packages" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "flow_type": "workflow"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 2373,
    "name": "AWS CloudFront Log Analysis",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T07:09:18Z",
    "updated_at": "2014-04-13T19:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2373",
    "html_url":"https://xplenty.com/xplenation/packages/2373",
    "status":"active",
    "data_processes_count":0,
    "running_data_processes_count":0,
    "idle_data_processes_count":0,
    "completed_data_processes_count":0,
    "pending_data_processes_count":0,
    "stopped_data_processes_count":0,
    "failed_data_processes_count":0,
    "pending_stoppage_data_processes_count":0,
    "stopping_data_processes_count":0,
    "job_validations_count":0,
    "running_job_validations_count":0,
    "completed_job_validations_count":0,
    "failed_job_validations_count":0
  },
  {
    "id": 2374,
    "name": "AWS CloudFront Log Analysis 2",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T08:09:18Z",
    "updated_at": "2014-04-13T20:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2374",
    "html_url":"https://xplenty.com/xplenation/packages/2374",
    "status":"active",
    "data_processes_count":0,
    "running_data_processes_count":0,
    "idle_data_processes_count":0,
    "completed_data_processes_count":0,
    "pending_data_processes_count":0,
    "stopped_data_processes_count":0,
    "failed_data_processes_count":0,
    "pending_stoppage_data_processes_count":0,
    "stopping_data_processes_count":0,
    "job_validations_count":0,
    "running_job_validations_count":0,
    "completed_job_validations_count":0,
    "failed_job_validations_count":0
  }
]
```
