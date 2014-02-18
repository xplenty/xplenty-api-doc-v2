## List Clusters

### Description
This call returns a list of clusters that were created by users in your account.
You can use this information to monitor and display your clusters and their statuses.
Optionally, you can use the input parameters to filter the cluster list so that it contains
only clusters with a specific status, and to determine the order by which the list will be sorted.

The details returned for each cluster are:

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
* **status** (optional) - Possible values are: ```pending```, ```creating```, ```available```, ```pending_terminate```, ```terminating```, ```terminated```, ```error```, ```all``` (default). The call will return only clusters with the given status, or all the clusters if the "all" value is specified. 
* **sort** (optional) - Possible values are: ```updated```, ```created``` (default). The cluster list will be sorted by the clusters' "updated_by" values or "created_by" values respectively, depending on the value of the "sort" parameter.
* **direction** (optional) - Possible values are: ```asc```, ```desc``` (default). The clusters will be sorted in ascending or descending order of the "sort" attribute, depending on the value of "direction".
* **since** (optional) - The cluster list will be filtered out of any clusters updated before the given time. The time should be passed in as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call)
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" 
    -u <APIkey>: "https://api-staging.xplenty.com/<accountID>/api/clusters?status=<statusFilter>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
```

### Response Example
```json
[
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
    },
    {
        "id": 98,
        "name": "Daily Outliers Test #101",
        "description": "Daily Outliers Test",
        "status": "terminated",
        "owner_id": 27,
        "plan_id": 1,
        "nodes": 2,
        "type": "production",
        "created_at": "2013-01-25T08:17:56Z",
        "updated_at": "2013-01-28T16:45:14Z",
        "available_since": "2013-01-28T08:23:12Z",
        "terminated_at": "2013-01-28T16:45:14Z",
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/98"
        "terminate_on_idle": false,
        "time_to_idle": 3600
    },
    {
        "id": 97,
        "name": "Daily Outliers Test #102",
        "description": "Daily Outliers Test",
        "status": "terminated",
        "owner_id": 27,
        "plan_id": null,
        "nodes": 0,
        "type": "sandbox",
        "created_at": "2013-01-25T07:36:04Z",
        "updated_at": "2013-01-25T07:45:19Z",
        "available_since": "2013-01-25T07:40:02Z",
        "terminated_at": "2013-01-25T07:45:19Z",
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/97"
        "terminate_on_idle": true,
        "time_to_idle": 3600
    }
]
```
