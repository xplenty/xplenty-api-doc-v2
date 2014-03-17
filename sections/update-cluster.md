## Update Cluster

### Description
This call updates the given cluster, including scaling a running cluster of type "production".

A successful call returns the following details for the cluster after the changes.

* **id** - the cluster's numeric identifier
* **name** - the name given to the cluster upon creation
* **description** - the description given to the cluster upon creation
* **status** - the cluster's status. Possible values are:
    * **pending** - the user sent a request to create the cluster
    * **creating** - the cluster is initializing
    * **available** - the cluster is initialized and is available to run jobs
    * **pending_terminate** - the user has sent a termination request for the cluster
    * **terminating** - the cluster is terminating
    * **terminated** - the cluster is no longer active
    * **error** - an error was encountered on the cluster
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

### Input Parameters
|Name|Required?|    Default|Description|
|----|---------|    -------|-----------|
|cluster_id|Y| |The id of the cluster to update
|nodes|N| |Determines the number of compute nodes in the cluster. The value range is between 2 and your account's maximum, determined by the chosen pricing plan|
name|N| |The name given to the cluster upon creation
description|N| |The description given to the cluster upon creation
terminate_on_idle|N| |If the value is set to either true, t or 1 this cluster will be terminated after it becomes idle
time_to_idle|N| |The time interval (in seconds) after which this cluster will become idle

### Request (Curl Call) Syntax
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
        "time_to_idle": 7200,
        "terminated_on_idle": false
    }
```
