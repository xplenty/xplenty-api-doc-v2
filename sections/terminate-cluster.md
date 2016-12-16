## Terminate Cluster

### Description
Terminate an existing [cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md), releasing its resources and terminating its runtime period.
Use this call when all of the cluster's jobs are completed and it's no longer needed.

### Notes
* This call only triggers the termination process, which is why a status of "pending_terminate" is returned.
You can verify that a cluster has terminated successfully by [retrieving the cluster's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-cluster-information.md) and checking for the "terminated" status.

### Input Parameters
The **cluster ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/clusters/:cluster_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 167,
  "name": "New Cluster",
  "description": "New Cluster Description",
  "status": "pending_terminate",
  "owner_id": 27,
  "plan_id": null,
  "nodes": 1,
  "type": "sandbox",
  "created_at": "2013-03-03T13:06:51Z",
  "updated_at": "2013-03-03T14:16:18Z",
  "available_since": "2013-03-03T13:09:22Z",
  "terminated_at": null,
  "running_jobs_count": 0,
  "running_data_processes_count":0,
  "idle_data_processes_count":0,
  "completed_data_processes_count":0,
  "pending_data_processes_count":0,
  "stopped_data_processes_count":0,
  "failed_data_processes_count":0,
  "pending_stoppage_data_processes_count":0,
  "stopping_data_processes_count":0,
  "completed_jobs_count":0,
  "idle_jobs_count":0,
  "pending_jobs_count":0,
  "stopped_jobs_count":0,
  "failed_jobs_count":0,
  "pending_stoppage_jobs_count":0,
  "stopping_jobs_count":0,
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
  "idle_since": "2013-03-03T13:06:51Z",
  "url": "https://api.xplenty.com/xplenation/api/clusters/167",
  "html_url": "https://xplenty.com/xplenation/clusters/167",
  "bootstrap_actions": [{
    "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
    "args": ["arg1", "arg2"]
  }, {
    "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
    "args": ["arg1"]
  }]
}
```
