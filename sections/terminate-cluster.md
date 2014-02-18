## Terminate Cluster

### Description
This call deactivates the given cluster, releasing its resources and terminating its runtime period.
Use this call when all of the cluster's jobs are completed and it's no longer needed.
The call returns the given cluster's details, including a status of "pending_terminate".

### Notes
* This call only triggers the termination process, which is why a status of "pending_terminate" is returned.
To verify termination, [get the cluster's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-cluster-information.md) and check for a status of "terminated".

### Input Parameters
The **cluster resource ID** must be supplied at the end of the request URL.

### Request (Curl Call)
```shell
    curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/clusters/<clusterID>"
```

### Response Example
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
        "time_to_idle": 3600
    }
```
