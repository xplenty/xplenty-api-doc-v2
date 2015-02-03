## Create Cluster

### Description
This call creates a new cluster. A cluster is a group of machines ("nodes") allocated to your account. The number of nodes in the cluster is determined by the "nodes" value that you supply to the call. While the cluster is active, only your account's users can run jobs on the cluster.
You will need to provide an active cluster when [starting a new job](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/run-job.md).

A successful call returns the following details for the new cluster:

* **id** - the cluster's numeric identifier
* **name** - the name given to the cluster upon creation
* **description** - the description given to the cluster upon creation
* **status** - the cluster's status. Possible values are:
    * **pending** - the user sent a request to create the cluster
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

### Notes
* This call only triggers cluster creation, and therefore it returns the "pending" status. You can run a job on a pending cluster, but if for any reason the cluster failed to initialize, the job will fail to run.
You can verify that a cluster has initialized successfully by [retrieving the cluster's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-cluster-information.md) and checking for the "available" status.
* You must save the cluster ID value returned in the response "id" field. You will use the value to refer to this cluster in subsequent API calls.

### Input Parameters
|Name|Required?|    Default|Description|
|----|---------|    -------|-----------|
|nodes|Y| |Determines the number of compute nodes in the cluster. The value range is between 2 and your account's maximum, determined by the chosen pricing plan|
type|N|production|If the value is set to "sandbox", a sandbox cluster is created and the "nodes" parameter is ignored
name|N|System generated|Name to assign to the new cluster
description|N|Blank|Description to assign to the new cluster
terminate_on_idle|N|false|If the value is set to either true, t or 1 this cluster will be terminated after it becomes idle
time_to_idle|N|3600 seconds (60 minutes)|The time interval (in seconds) after which this cluster will become idle
region|N|Account region setting|The region in which the cluster should be created|
zone|N||The zone in which the cluster should be created (for availability zone supported regions)|

### Request (Curl Call) Example
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/clusters" 
	-d "cluster[nodes]=4"
	-d "cluster[type]=production"
	-d "cluster[name]=<clusterName>" 
	-d "cluster[description]=<clusterDescription>"
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```

```json
{
	"id": 167,
	"name": "New Cluster",
	"description": "New Cluster Description",
	"status": "pending",
	"owner_id": 27,
	"plan_id": null,
	"nodes": 4,
	"type": "production",
	"created_at": "2013-03-03T13:06:51Z",
	"updated_at": "2013-03-03T13:06:51Z",
	"available_since": null,
	"terminated_at": null,
	"running_jobs_count": 0,
	"url": "https://api.xplenty.com/xplenation/api/clusters/167",
	"terminate_on_idle": false,
	"time_to_idol": 3600,
	"terminated_on_idle": false,
	"region": "amazon-web-services::us-east-1",
	"zone": "us-east-1b"
}
```
