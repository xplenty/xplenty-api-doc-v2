## List Schedules

### Description
List [schedules](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md) that are accessible by authenticated user.
You can use this information to monitor your schedules and their status.
Optionally, you can supply the input parameters to filter the schedule list so that it contains only schedules with a specific status, and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
status|N|"all"|Possible values are any status listed in [Schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md) resource or ```all```. The call will return only schedules with the given status, or all the schedules if the "all" value is specified.
sort|N|"created"|Possible values are ```updated``` or ```created```. The schedule list will be sorted by the schedules' "updated_at" or "created_at" value respectively.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The schedules will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The schedule list will only contain schedules updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/schedules" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json"
```
### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "created_at": "2014-09-25T08:48:51Z",
    "name": "My Schedule",
    "description": "A daily schedule",
    "execution_count": 0,
    "id": 2,
    "auto_retry": true,
    "auto_retry_attempts": 4,
    "interval_amount": 1,
    "interval_unit": "days",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
    "overlap":true,
    "reuse_cluster_strategy":"any",
    "task": {
      "nodes": 3,
      "packages": [
        {
          "package_id": "1",
          "variables": {
            "MY_VAR": "'My Var Value'"
          }
        }
      ],
      "terminate_on_idle": true,
      "time_to_idle": 60
    },
    "updated_at": "2014-10-29T14:22:05Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/2",
    "html_url": "https://xplenty.com/xplenation/schedules/2"
  },
  {
    "created_at": "2014-09-25T08:48:51Z",
    "name": "My Schedule",
    "description": "A monthly schedule",
    "execution_count": 0,
    "id": 2,
    "auto_retry": false,
    "auto_retry_attempts": 3,
    "interval_amount": 1,
    "interval_unit": "months",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
    "overlap":false,
    "reuse_cluster_strategy":"none",
    "task": {
      "nodes": 3,
      "packages": [
        {
          "package_id": "1",
          "variables": {
            "MY_VAR": "'My Var Value'"
          }
        }
      ],
      "terminate_on_idle": true,
      "time_to_idle": 60
    },
    "updated_at": "2014-10-29T14:22:05Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/2",
    "html_url": "https://xplenty.com/xplenation/schedules/2"
  },
  {
    "created_at": "2014-09-25T08:48:51Z",
    "name": "My Schedule",
    "description": "An hourly schedule (every 2 hours)",
    "execution_count": 0,
    "id": 2,
    "auto_retry": false,
    "auto_retry_attempts": 3,
    "interval_amount": 2,
    "interval_unit": "hours",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
    "overlap":true,
    "reuse_cluster_strategy":"self",
    "task": {
      "nodes": 3,
      "packages": [
        {
          "package_id": "1",
          "variables": {
            "MY_VAR": "'My Var Value'"
          }
        }
      ],
      "terminate_on_idle": true,
      "time_to_idle": 60
    },
    "updated_at": "2014-10-29T14:22:05Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/2",
    "html_url": "https://xplenty.com/xplenation/schedules/2"
  }
]
```
