## List Jobs

### Description
List [jobs](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md) that are accessible by the authenticated user.
You can use this information to monitor your jobs and their status.
Optionally, you can supply the input parameters to filter the job list so that it contains only jobs with a specific status, and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
status|N|"all"|Possible values are any status listed in [Job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md) resource or ```all```. The call will return only jobs with the given status, or all the clusters if the "all" value is specified.
sort|N|"created"|Possible values are ```updated``` or ```created```. The job list will be sorted by the jobs' "updated_at" or "created_at" value respectively.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The jobs will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The job list will only contain jobs updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```
### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 304,
    "status": "failed",
    "variables":
    {
        "InputPath": "'/today'"
    },
    "owner_id": 1,
    "progress": 0,
    "outputs_count": 0,
    "outputs": [],
    "started_at": "2013-03-04T08:02:20Z",
    "created_at": "2013-03-04T08:02:17Z",
    "updated_at": "2013-03-04T08:03:01Z",
    "failed_at": null,
    "cluster_id": 176,
    "package_id": 103,
    "errors": "Package failed to execute.",
    "runtime_in_seconds": 40,
    "completed_at": "2013-03-04T08:03:01Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/304",
    "html_url": "https://xplenty.com/xplenation/jobs/304",
    "log_url": "https://api.xplenty.com/xplenation/api/jobs/304/log",
    "creator":
    {
        "type":"Schedule",
        "id":1,
        "display_name": "Schedule 1",
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    },
    "package": {
      "id": 2373,
      "name": "AWS CloudFront Log Analysis",
      "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
      "variables": {},
      "owner_id": 8,
      "created_at": "2014-03-12T07:09:18Z",
      "updated_at": "2014-04-13T19:38:04Z",
      "url": "https://api.xplenty.com/xplenation/api/packages/2373",
      "status":"active"
    },
    "cluster": {
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
          "id":1,
          "display_name": "Schedule 1",
          "url": "https://api.xplenty.com/xplenation/api/schedules/1",
          "html_url": "https://xplenty.com/xplenation/schedules/1"
      }
    },
  },
  {
    "id": 303,
    "status": "failed",
    "variables": {},
    "owner_id": 1,
    "progress": 0,
    "outputs_count": 0,
    "outputs": [],
    "started_at": "2013-03-04T07:38:33Z",
    "created_at": "2013-03-04T07:38:27Z",
    "updated_at": "2013-03-04T07:39:11Z",
    "failed_at": null,
    "cluster_id": 176,
    "package_id": 434,
    "errors": "Package failed to execute.",
    "runtime_in_seconds": 38,
    "completed_at": "2013-03-04T07:39:11Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/303",
    "html_url": "https://xplenty.com/xplenation/jobs/303",
    "log_url": "https://api.xplenty.com/xplenation/api/jobs/303/log",
    "creator":
    {
        "type":"Schedule",
        "id":1,
        "display_name": "Schedule 1",
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    },
    "package": {
      "id": 2373,
      "name": "AWS CloudFront Log Analysis",
      "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
      "variables": {},
      "owner_id": 8,
      "created_at": "2014-03-12T07:09:18Z",
      "updated_at": "2014-04-13T19:38:04Z",
      "url": "https://api.xplenty.com/xplenation/api/packages/2373",
      "status":"active"
    },
    "cluster": {
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
          "id":1,
          "display_name": "Schedule 1",
          "url": "https://api.xplenty.com/xplenation/api/schedules/1",
          "html_url": "https://xplenty.com/xplenation/schedules/1"
      }
    },
  },
  {
    "id": 299,
    "status": "stopped",
    "variables": {},
    "owner_id": 1,
    "progress": 0,
    "outputs_count": 0,
    "outputs": [],
    "started_at": null,
    "created_at": "2013-03-04T06:58:48Z",
    "updated_at": "2013-03-04T07:17:51Z",
    "failed_at": null,
    "cluster_id": 176,
    "package_id": 434,
    "errors": "Package failed to execute.",
    "runtime_in_seconds": 0,
    "completed_at": "2013-03-04T07:17:51Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/299",
    "html_url": "https://xplenty.com/xplenation/jobs/299",
    "log_url": "https://api.xplenty.com/xplenation/api/jobs/299/log",
    "creator":
    {
        "type":"User",
        "id":1,
        "display_name": "Schedule 1",
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    },
    "package": {
      "id": 2373,
      "name": "AWS CloudFront Log Analysis",
      "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
      "variables": {},
      "owner_id": 8,
      "created_at": "2014-03-12T07:09:18Z",
      "updated_at": "2014-04-13T19:38:04Z",
      "url": "https://api.xplenty.com/xplenation/api/packages/2373",
      "status":"active"
    },
    "cluster": {
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
          "id":1,
          "display_name": "Schedule 1",
          "url": "https://api.xplenty.com/xplenation/api/schedules/1",
          "html_url": "https://xplenty.com/xplenation/schedules/1"
      }
    },
  },
  {
    "id": 157,
    "status": "completed",
    "variables": {},
    "owner_id": 1,
    "progress": 1,
    "outputs_count": 2,
    "outputs": [
      {
        "component": {
          "name": "destination7",
          "type": "cloud_storage_destination_component",
          "fields": [
            "id",
            "account_name"
          ]
        },
        "created_at": "2013-03-04T07:17:51Z",
        "id": 521,
        "name": "projected_results",
        "preview_url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521/preview",
        "records_count": 10415234,
        "updated_at": "2013-03-04T07:17:51Z",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521"
      },
      {
        "component": {
          "name": "destination7",
          "type": "cloud_storage_destination_component",
          "fields": [
            "id",
            "account_name"
          ]
        },
        "created_at": "2013-03-04T07:14:44Z",
        "id": 522,
        "name": "projected_results2",
        "preview_url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522/preview",
        "records_count": 423,
        "updated_at": "2013-03-04T07:14:44Z",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522"
      },
    ],
    "started_at": "2012-12-30T14:21:29Z",
    "created_at": "2012-12-30T14:21:18Z",
    "updated_at": "2012-12-30T14:29:29Z",
    "cluster_id": 52,
    "package_id": 434,
    "errors": "",
    "runtime_in_seconds": 417,
    "completed_at": "2012-12-30T14:29:29Z",
    "url": "https://api.xplenty.com/xplenation/api/jobs/157",
    "html_url": "https://xplenty.com/xplenation/jobs/157",
    "log_url": "https://api.xplenty.com/xplenation/api/jobs/157/log",
    "creator":
    {
        "type":"Schedule",
        "id":2,
        "display_name": "Schedule 2",
        "url": "https://api.xplenty.com/xplenation/api/schedules/2",
        "html_url": "https://xplenty.com/xplenation/schedules/2"
    },
    "package": {
      "id": 2373,
      "name": "AWS CloudFront Log Analysis",
      "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
      "variables": {},
      "owner_id": 8,
      "created_at": "2014-03-12T07:09:18Z",
      "updated_at": "2014-04-13T19:38:04Z",
      "url": "https://api.xplenty.com/xplenation/api/packages/2373",
      "status":"active"
    },
    "cluster": {
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
          "id":1,
          "display_name": "Schedule 1",
          "url": "https://api.xplenty.com/xplenation/api/schedules/1",
          "html_url": "https://xplenty.com/xplenation/schedules/1"
      }
    },
  }
]
```
