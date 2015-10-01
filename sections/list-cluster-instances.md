## List Cluster Instances

### Description
List existing cluster [instances](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster-instance.md).

Note: This endpoint is only available for selected plans.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/clusters/:cluster_id/instances" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "instance_id": "i-4d1b39a7",
    "private_dns": "ip-10-124-29-23.ec2.internal",
    "public_dns": "ec2-55-27-210-201.compute-1.amazonaws.com",
    "status": "available",
    "master": true,
    "spot": false,
    "url":"https://api.xplenty.com/xplenation/api/clusters/5/instances/i-4d1b39a7"
  },
  {
    "instance_id": "i-4d1b39a8",
    "private_dns": "ip-10-132-30-26.ec2.internal",
    "public_dns": "ec2-52-27-210-201.compute-1.amazonaws.com",
    "status": "available",
    "master": false,
    "spot": false,
    "url":"https://api.xplenty.com/xplenation/api/clusters/5/instances/i-4d1b39a8"
  },
  {
    "instance_id": "i-4d1b39a9",
    "private_dns": "ip-10-112-30-26.ec2.internal",
    "public_dns": "ec2-59-23-93-132.compute-1.amazonaws.com",
    "status": "available",
    "master": false,
    "spot": true,
    "url":"https://api.xplenty.com/xplenation/api/clusters/5/instances/i-4d1b39a9"
  }
]
```
