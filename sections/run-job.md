## Run Job

### Description
Create a new [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md) and trigger it to run. The job performs the series of data processing tasks that are defined in the job's package. Unless the job encounters an error or is terminated by the user, it will run until it completes its tasks on all of the input data.

### Notes
* You must save the job ID value returned in the response "id" field. You will use the value to refer to this job in subsequent API calls.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
cluster_id|Y| |the ID of the cluster on which to run the job
package_id|Y| |the ID of the package the job will perform
variables|N| |If the package has input variables, you can supply their names and values in the run request. See the syntax below.
dynamic_variables|N| |If the package has dynamic input variables, that use expressions as values, you can supply their names and values in the run request. See the syntax below.

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/jobs" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "cluster_id":1,
    "package_id":2,
    "dynamic_variables":{
      "current_time":"CurrentTime()",
      "MY_CURRENT_TIME":"$CURRENT_TIME_VAR",
      "MY_STRING_VAR":"'some string'"
    },
    "variables": {
      "MY_STATIC_VAR":"some static variable"
    }
  }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
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
      "records_count": 10415234,
      "updated_at": "2013-03-04T07:17:51Z",
      "url": "https://api.xplenty.com/xplenation/api/jobs/299/outputs/521",
    },
    {
      "component_name": "destination2",
      "created_at": "2013-03-04T07:14:44Z",
      "id": 522,
      "name": "projected_results2",
      "records_count": 423,
      "updated_at": "2013-03-04T07:14:44Z",
      "url": "https://api.xplenty.com/xplenation/api/jobs/299/outputs/522",
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
  "completed_at": "2012-12-30T14:29:29Z",
  "url": "https://api.xplenty.com/xplenation/api/jobs/157",
  "html_url": "https://xplenty.com/xplenation/jobs/157",
  "log_url": "https://api.xplenty.com/xplenation/api/jobs/157/log",
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
}
```
