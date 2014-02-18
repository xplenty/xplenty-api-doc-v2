## Update Cluster

### Description
This call updates the given cluster. This method can also be used to scale a running cluster of type "production".
The call returns the given cluster's details after the changes.

### Input Parameters
* **cluster_id** - the ID of the cluster to update
* **name** - the name given to the cluster upon creation
* **description** - the description given to the cluster upon creation
* **nodes** - the number of compute nodes for the cluster
* **terminate_on_idle** - indicates whether the cluster will be terminated after it becomes idle
* **time_to_idle** - the time interval (in seconds) in which the cluster will become idle

### Request (Curl Call)
```shell
    curl -X PUT -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/clusters/<clusterID>"
    -d "cluster[nodes]=4"
    -d "cluster[name]=<clusterName>" 
    -d "cluster[description]=<clusterDescription>"
    -d "cluster[terminate_on_idle]=1"
    -d "cluster[time_to_idle]=7200"
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
        "nodes": 4,
        "type": "production",
        "created_at": "2013-03-03T13:06:51Z",
        "updated_at": "2013-03-03T14:16:18Z",
        "available_since": "2013-03-03T13:09:22Z",
        "terminated_at": null,        
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/167",
        "terminate_on_idle": true,
        "time_to_idle": 7200
    }
```
