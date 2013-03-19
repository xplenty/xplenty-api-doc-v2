## Get Cluster Information

### Description
This call returns the details of the cluster with the given ID, as follows:

* **id** - the cluster's numeric identifier
* **name** - the name given to the cluster upon creation
* **description** - the description given to the cluster upon creation
* **status** - the cluster's status. Possible values are:
    * **pending** - the cluster has just been created
    * **creating** - the cluster is initializing
    * **available** - the cluster is initialized and is available to run jobs
    * **pending_terminate** - the user has sent a termination request for the cluster
    * **terminating** - the cluster is terminating
    * **terminated** - the cluster is no longer active
    * **error** - an error was encountered on the cluster
* **owner_id** - the numeric user ID
* **plan_id** - the ID of the cluster's plan
* **created_at** - the date and time the cluster was created
* **updated_at** - the date and time the cluster was last updated. 
* **running_jobs_count** - the number of jobs currently running on the cluster
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
        "id": 167,
        "name": "New Cluster",
        "description": "New Cluster Description",
        "status": "available",
        "owner_id": 27,
        "plan_id": 1,
        "created_at": "2013-03-03T13:06:51Z",
        "updated_at": "2013-03-03T13:13:19Z",
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/167"
    }
```
