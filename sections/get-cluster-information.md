## Get Cluster Information

### Description
This call returns the details of the cluster with the given ID, as follows:

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
* **type** - the type of the cluster ("sandbox" or "production")
* **nodes** - the number of compute nodes for the cluster
* **created_at** - the date and time the cluster was created
* **updated_at** - the date and time the cluster was last updated
* **available_since** - the date and time the cluster became available
* **terminated_at** - the date and time the cluster was terminated
* **running_jobs_count** - the number of jobs currently running on the cluster
* **terminate_on_idle** - indicates whether the cluster will be terminated after it becomes idle
* **time_to_idle** - the time interval (in seconds) in which the cluster will become idle
* **url** - the unique cluster resource URL


### Input Parameters
The **cluster resource ID** must be supplied at the end of the request URL.

### Request (Curl Call)
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/clusters/<clusterID>"
```

### Response Example
```json
    {
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
        "url": "https://api.xplenty.com/xplenation/api/clusters/99",
        "terminate_on_idle": false,
        "time_to_idle": 3600
    }
```
