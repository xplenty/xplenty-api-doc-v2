## Get Cluster Information

### Description
Info for an existing [cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md).

### Input Parameters
The **cluster ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/clusters/:cluster_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

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
  "bootstrap_actions": [{
    "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
    "args": ["arg1", "arg2"]
  }, {
    "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
    "args": ["arg1"]
  }],
  "creator":
  {
      "type":"Schedule",
      "display_name": "Schedule 1",
      "id":1,
      "url": "https://api.xplenty.com/xplenation/api/schedules/1",
      "html_url": "https://xplenty.com/xplenation/schedules/1"
  }
}
```
