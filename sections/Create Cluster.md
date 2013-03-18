## Create Cluster

### Description
This call creates a new cluster. A cluster is a group of machines ("nodes") allocated to your account. The number of nodes in the cluster is determined by the "plan_id" value that you supply to the call. While the cluster is active, only your account's users can run jobs on the cluster.
You will need to provide an active cluster when [starting a new job](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/Run%20Job.md).

A successful call returns the following details for the new cluster:
* **id** - the cluster's numeric identifier
* **name** - the name supplied to the call
* **description** - the description supplied to the call
* **status** - the cluster's status ("pending" for a new cluster).
* **owner_id** - the numeric user ID
* **plan_id** - the ID of the cluster's plan
* **created_at** - the date and time the cluster was created
* **updated_at** - same value as "created_at" for a new cluster
* **running_jobs_count** - the number of jobs currently running on the cluster (0 for a new cluster)
* **url** - the unique cluster resource URL
  
### Notes
* This call only triggers cluster creation, which is why it returns the "pending" status. You can run a job on a pending cluster, but if for any reason the cluster failed to initialize, the job will fail to run.
You can verify that a cluster has initialized successfully by [getting the cluster's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/Get%20Cluster%20Information.md) and checking for the "available" status.
* Save the cluster ID value returned in the response "id" field. You will use the value to refer to this cluster in subsequent API calls.

### Input Parameters
* plan_id - the cluster plan to use when creating the cluster (determines the number of nodes in the cluster and its pricing)
* name (optional) - a name to assign to the new cluster. If not supplied, the system will generate a name for the cluster.
* description (optional) - a description to assign to the new cluster. If not supplied, the description will remain blank.

### Request (Curl Call)
```shell
    curl -X POST -H "Accept: application/vnd.xplenty+json" -u <APIkey>:"https://api.xplenty.com/<accountID>/api/clusters" 
    -d "cluster[plan_id]=<clusterPlanID>" 
    -d "cluster[name]=<clusterName>" 
    -d "cluster[description]=<clusterDescription>"
```

### Response Example
```json
    {
        "id": 167,
        "name": "New Cluster",
        "description": "New Cluster Description",
        "status": "pending",
        "owner_id": 27,
        "plan_id": 1,
        "created_at": "2013-03-03T13:06:51Z",
        "updated_at": "2013-03-03T13:06:51Z",
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/167"
    }
```
