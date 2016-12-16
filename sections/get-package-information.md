## Get Package Information

### Description
Info for an existing [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md).

### Input Parameters
The **package ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/packages/:package_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 2373,
  "name": "AWS CloudFront Log Analysis",
  "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
  "variables": {},
  "owner_id": 8,
  "created_at": "2014-03-12T07:09:18Z",
  "updated_at": "2014-04-13T19:38:04Z",
  "url": "https://api.xplenty.com/xplenation/api/packages/2373",
  "html_url":"https://xplenty.com/xplenation/packages/3",
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
```
