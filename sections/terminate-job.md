## Terminate Job

### Description
Stop an active [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md). Usually it's not necessary to request to terminate a job, because the job will end when its tasks are completed. You may want to actively terminate a job if you need its cluster resources for a more urgent job, or if the job is taking too long to complete.

### Notes
* This call only triggers the job's termination, which is why a status of "pending_stoppage" is returned. To verify stoppage, [get the job's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-information.md) and check for a status of "stopped".
* If a job is stopped by the user, it may return only partial results or none at all, depending on its tasks and its stage at the time of stoppage.

### Input Parameters
The **job ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 305,
  "status": "pending_stoppage",
  "variables": 
  {
    "InputPath": "'/today'"
  },
  "owner_id": 1,
  "progress": 0,
  "outputs_count": 0,
  "started_at": "2013-03-04T08:10:48Z",
  "created_at": "2013-03-04T08:10:42Z",
  "updated_at": "2013-03-04T08:11:27Z",
  "failed_at": null,
  "cluster_id": 176,
  "package_id": 103,
  "errors": null,
  "runtime_in_seconds": 40,
  "completed_at": null,
  "url": "https://api.xplenty.com/xplenation/api/jobs/305",
  "html_url": "https://xplenty.com/xplenation/jobs/305",
  "log_url": "https://api.xplenty.com/xplenation/api/jobs/305/log",
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