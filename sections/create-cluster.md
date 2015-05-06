## Create Cluster

### Description
Create a new [cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md).

### Notes
* This call only triggers cluster creation, and therefore it returns the "pending" status. You can run a job on a pending cluster, but if for any reason the cluster failed to initialize, the job will fail to run.
You can verify that a cluster has initialized successfully by [retrieving the cluster's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-cluster-information.md) and checking for the "available" status.
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
master_instance_type|N||The type of the master instance|
slave_instance_type|N||The type of the slave instance|
master_spot_price|N||The maximum bid price (in USD) requested for master spot instance|
slave_spot_price|N||The maximum bid price (in USD) requested for slave spot instance|
master_spot_percentage|N||The percentage of master instances requested as spot (value between 0 and 1)|
slave_spot_percentage|N||The percentage of slave instances requested as spot (value between 0 and 1)|
allow_fallback|N||If the value is set to either true, t or 1 instances will be created as on-demand instances if spot requests are not fulfilled|
stack|N|"white-everest"|The stack of the cluster|

### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/clusters" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "nodes":4,
    "type":"production",
    "name":"New Cluster",
    "description":"New Cluster Description"
  }'
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
  "terminate_on_idle": false,
  "time_to_idol": 3600,
  "terminated_on_idle": false,
  "region": "amazon-web-services::us-east-1",
  "zone": "us-east-1b",
  "master_instance_type": "m3.xlarge",
  "slave_instance_type": "m3.xlarge",
  "master_spot_price": null,
  "slave_spot_price": 0.153,
  "master_spot_percentage": null,
  "slave_spot_percentage": 0.5,
  "allow_fallback": true,
  "stack": "white-everest",
  "url": "https://api.xplenty.com/xplenation/api/clusters/167"
}
```
