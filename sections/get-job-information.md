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
  "package": {
    "id": 2373,
    "name": "AWS CloudFront Log Analysis",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T07:09:18Z",
    "updated_at": "2014-04-13T19:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2373",
    "status":"active"
  },
  "cluster": {
     "id": 99,
    "name": "Daily Outliers Test #100",
    "description": "Daily Outliers Test",
    "status": "terminated",
    "owner_id": 27,
    "plan_id": 1,
    "nodes": 2,
    "type": "production",
    "created_at": "2013-01-25T08:18:39Z",
    "updated_at": "2013-01-28T16:45:24Z",
    "available_since": "2013-01-28T16:46:22Z",
    "terminated_at": "2013-01-28T17:45:33Z",
    "running_jobs_count": 0,
    "terminate_on_idle": false,
    "time_to_idle": 3600,
    "terminated_on_idle": false,
    "region": "amazon-web-services::us-east-1",
    "zone": "us-east-1b",
    "master_instance_type": "m3.xlarge",
    "slave_instance_type": "m3.xlarge",
    "master_spot_price": null,
    "slave_spot_price": null,
    "master_spot_percentage": null,
    "slave_spot_percentage": null,
    "allow_fallback": true,
    "stack": "white-everest",
    "url": "https://api.xplenty.com/xplenation/api/clusters/99",
    "html_url": "https://xplenty.com/xplenation/clusters/99",
    "bootstrap_actions": [{
      "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
      "args": ["arg1", "arg2"]
    }, {
      "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
      "args": ["arg1"]
    }],
    "creator":
    {
        "type":"Schedule",
        "id":1,
        "display_name": "Schedule 1",
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    }
  },
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
  "html_url": "https://xplenty.com/xplenation/jobs/157",
  "log_url": "https://api.xplenty.com/xplenation/api/jobs/157/log",
  "creator":
  {
      "type":"Schedule",
      "id":1,
      "display_name": "Schedule 1",
      "url": "https://api.xplenty.com/xplenation/api/schedules/1",
      "html_url": "https://xplenty.com/xplenation/schedules/1"
  }
}
```
