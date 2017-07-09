## List Clusters

### Description
List [clusters](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) that are accessible by the authenticated user.
You can use this information to monitor and display your clusters and their status.
Optionally, you can supply the input parameters to filter the cluster list so that it contains only clusters with a specific status, and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
status|N|"all"|Possible values are any status listed in [Cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) resource or ```all```. The call will return only clusters with the given status, or all the clusters if the "all" value is specified.
sort|N|"created"|Possible values are ```updated``` or ```created```. The cluster list will be sorted by the clusters' "updated_at" or "created_at" value respectively.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The clusters will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The cluster list will only contain clusters updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/clusters" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

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
    "terminate_on_idle": false,
    "time_to_idle": 3600,
    "terminated_on_idle": false,
    "region": "amazon-web-services::us-east-1",
    "zone": "us-east-1b",
    "master_instance_type": "m3.xlarge",
    "slave_instance_type": "m3.xlarge",
    "master_spot_price": null,
    "slave_spot_price": null,
    "master_spot_percentage": null,
    "slave_spot_percentage": null,
    "allow_fallback": true,
    "stack": "white-everest",
    "idle_since": "2013-03-03T13:06:51Z",
    "url": "https://api.xplenty.com/xplenation/api/clusters/99",
    "html_url": "https://xplenty.com/xplenation/clusters/99",
    "creator":
    {
        "type":"Schedule",
        "display_name": "Schedule 1",
        "id":1,
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    }
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
    "terminate_on_idle": false,
    "time_to_idle": 3600,
    "terminated_on_idle": false,
    "region": "amazon-web-services::us-east-1",
    "zone": "us-east-1d",
    "master_instance_type": "m3.xlarge",
    "slave_instance_type": "m3.xlarge",
    "master_spot_price": null,
    "slave_spot_price": null,
    "master_spot_percentage": null,
    "slave_spot_percentage": null,
    "allow_fallback": true,
    "stack": "white-everest",
    "idle_since": "2013-03-03T13:06:51Z",
    "url": "https://api.xplenty.com/xplenation/api/clusters/98",
    "html_url": "https://xplenty.com/xplenation/clusters/98",
    "bootstrap_actions": [{
      "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
      "args": ["arg1", "arg2"]
    }, {
      "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
      "args": ["arg1"]
    }]
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
    "terminate_on_idle": true,
    "time_to_idle": 3600,
    "terminated_on_idle": true,
    "region": "amazon-web-services::us-east-1",
    "zone": "us-east-1c",
    "master_instance_type": "m3.xlarge",
    "slave_instance_type": "m3.xlarge",
    "master_spot_price": null,
    "slave_spot_price": null,
    "master_spot_percentage": null,
    "slave_spot_percentage": null,
    "allow_fallback": true,
    "stack": "white-everest",
    "idle_since": "2013-03-03T13:06:51Z",
    "url": "https://api.xplenty.com/xplenation/api/clusters/97",
    "html_url": "https://xplenty.com/xplenation/clusters/97"
  }
]
```
