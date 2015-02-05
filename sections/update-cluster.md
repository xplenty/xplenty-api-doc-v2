## Update Cluster

### Description
This call updates the given [cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md), including scaling a running cluster of type "production".

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
  "terminated_on_idle": false,
  "region": "amazon-web-services::us-east-1",
  "zone": "us-east-1c",
  "master_instance_type": "m3.xlarge",
  "slave_instance_type": "m3.xlarge",
  "master_spot_price": null,
  "slave_spot_price": null,
  "master_spot_percentage": null,
  "slave_spot_percentage": null,
  "allow_fallback": true
}
```
