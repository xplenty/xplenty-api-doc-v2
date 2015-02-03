## List Schedules

### Description
This call returns information for the list of schedules that were created by users in your account.
You can use this information to monitor your schedules and their status.
Optionally, you can supply the input parameters to filter the schedule list so that it contains only schedules with a specific status, and to determine the order by which the list will be sorted.

The details returned for each schedule are:

* **id** the numeric schedule ID
* **name** the name given to the schedule upon creation
* **description** the description given to the schedule upon creation
* **owner_id** the numeric user id of the package owner
* **status** the schedule's status. Possible values are:
    * **enabled**
    * **disabled**
* **start_at** the date and time when the schedule should start executing
* **next_run_at** the date and time the schedule's task will run next
* **interval_amount** number of interval units between schedule's task executions
* **interval_unit** Possible values are:
    * **minutes**
    * **hours**
    * **days**
    * **weeks**
    * **months**
* **task**
* **last_run_at** the date and time that schedule's task ran last
* **last_run_status** status of the last execution of the schedule's task
* **execution_count** number of times the schedule has run
* **created_at** the date and time the schedule was created
* **updated_at** the date and time the schedule was updated
* **url** the schedule resource ID


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
status|N|"all"|Possible values are any status listed above or ```all```. The call will return only schedules with the given status, or all the schedules if the "all" value is specified.
sort|N|"created"|Possible values are ```updated``` or ```created```. The schedule list will be sorted by the schedules' "updated_at" or "created_at" value respectively.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The schedules will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The schedule list will only contain schedules updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.


### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules?status=<statusFilter>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
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
    "interval_amount": 1,
    "interval_unit": "days",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
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
    "url": "https://api.xplenty.com/xplenation/api/schedules/2"
  },
  {
    "created_at": "2014-09-25T08:48:51Z",
    "name": "My Schedule",
    "description": "A monthly schedule",
    "execution_count": 0,
    "id": 2,
    "interval_amount": 1,
    "interval_unit": "months",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
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
    "url": "https://api.xplenty.com/xplenation/api/schedules/2"
  },
  {
    "created_at": "2014-09-25T08:48:51Z",
    "name": "My Schedule",
    "description": "An hourly schedule (every 2 hours)",
    "execution_count": 0,
    "id": 2,
    "interval_amount": 2,
    "interval_unit": "hours",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
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
    "url": "https://api.xplenty.com/xplenation/api/schedules/2"
  }
]
```
