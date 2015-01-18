## List Cluster Instances

### Description
This call returns information for a list of [cluster instance](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster-instance.md) that were allocated for the specified cluster.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/clusters/<clusterID>/instances"
```

### Response Example
```json
[
  {
    "instance_id": "i-4d1b39a7",
    "private_dns": "ip-10-124-29-23.ec2.internal",
    "public_dns": "ec2-55-27-210-201.compute-1.amazonaws.com",
    "status": "available",
    "master": true,
    "spot": false
  },
  {
    "instance_id": "i-4d1b39a8",
    "private_dns": "ip-10-132-30-26.ec2.internal",
    "public_dns": "ec2-52-27-210-201.compute-1.amazonaws.com",
    "status": "available",
    "master": false,
    "spot": false
  },
  {
    "instance_id": "i-4d1b39a9",
    "private_dns": "ip-10-112-30-26.ec2.internal",
    "public_dns": "ec2-59-23-93-132.compute-1.amazonaws.com",
    "status": "available",
    "master": false,
    "spot": true
  }
]
```
