## Get Job Information

### Description
Info for an existing [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md).

You can preview the output, which will display up to 100 lines, using the preview_url listed in the outputs of the response. 
View [Preview Job Output](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/preview-output.md) for details.

### Input Parameters
The **job resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
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
      "preview_url": "https://api.xplenty.com/xplentation/api/jobs/157/outputs/521/preview",
      "records_count": 10415234,
      "updated_at": "2013-03-04T07:17:51Z",
      "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521"
    },
    {
      "component_name": "destination2",
      "created_at": "2013-03-04T07:14:44Z",
      "id": 522,
      "name": "projected_results2",
      "preview_url": "https://api.xplenty.com/xplentation/api/jobs/157/outputs/522/preview",
      "records_count": 423,
      "updated_at": "2013-03-04T07:14:44Z",
      "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522"
    },
  ],
  "started_at": "2012-12-30T14:21:29Z",
  "created_at": "2012-12-30T14:21:18Z",
  "failed_at": null,
  "updated_at": "2012-12-30T14:29:29Z",
  "cluster_id": 52,
  "package_id": 434,
  "errors": "",
  "runtime_in_seconds": 417,
  "completed_at": null,
  "url": "https://api.xplenty.com/xplenation/api/jobs/157",
  "creator":
  {
      "type":"Schedule",
      "id":1,
      "url":"http://api.xplenty.com/xplenation/api/schedules/1"
  }
}
```
