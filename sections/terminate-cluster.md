## Terminate Cluster

### Description
This call deactivates the given cluster, releasing its resources and terminating its runtime period.
Use this call when all of the cluster's jobs are completed and it's no longer needed.

A successful call returns the following details for the given cluster.

* **id** - the cluster's numeric identifier
* **name** - the name given to the cluster upon creation
* **description** - the description given to the cluster upon creation
* **status** - the cluster's status, pending_terminate. 
* **owner_id** - the numeric user ID of the cluster's owner
* **plan_id** - the ID of the cluster's plan
* **nodes** - the number of compute nodes for the cluster
* **type** - the type of the cluster ("sandbox" or "production")
* **created_at** - the date and time the cluster was created
* **updated_at** - the date and time the cluster was last updated
* **available_since** - the date and time the cluster became available
* **terminated_at** - the date and time the cluster was terminated
* **running_jobs_count** - the number of jobs currently running on the cluster
* **url** - the unique cluster resource URL
* **terminate_on_idle** - indicates whether the cluster will be terminated after it becomes idle
* **time_to_idle** - the time interval (in seconds) in which the cluster will become idle
* **terminated_on_idle** - indicates whether the cluster terminated because it became idle
* **region** - the region in which the cluster was created
* **zone** - the zone in which the cluster was created

### Notes
* This call only triggers the termination process, which is why a status of "pending_terminate" is returned.
You can verify that a cluster has terminated successfully by [retrieving the cluster's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-cluster-information.md) and checking for the "terminated" status.

### Input Parameters
The **cluster resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/clusters/<clusterID>"
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
  "url": "https://api.xplenty.com/xplenation/api/clusters/167",
  "terminate_on_idle": false,
  "time_to_idle": 3600,
  "terminated_on_idle": false,
  "region": "amazon-web-services::us-east-1",
  "zone": "us-east-1b"
}
```
