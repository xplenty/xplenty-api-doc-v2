## List Jobs

### Description
This call returns information for the list of schedules that were created by users in your account.
You can use this information to monitor your schedules and their status.
Optionally, you can supply the input parameters to filter the schedule list so that it contains only schedules with a specific status, and to determine the order by which the list will be sorted.

The details returned for each schedule are:


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
status|N|"all"|Possible values are any status listed above or ```all```. The call will return only schedules with the given status, or all the schedules if the "all" value is specified.
sort|N|"created"|Possible values are ```updated``` or ```created```. The schedule list will be sorted by the schedules' "updated_by" or "created_by" value respectively.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The scheduless will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The schedule list will only contain schedules updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.


### Request (Curl Call) Syntax
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json"
    -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules?status=<statusFilter>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
```
### Response Example
```json
[
  {
    "created_at": "2014-10-18T16:42:18Z",
    "day_of_week": null,
    "description": "",
    "end_at": null,
    "execution_count": 0,
    "id": 6,
    "interval_amount": 1,
    "interval_unit": "hours",
    "last_run_at": null,
    "last_run_status": null,
    "name": "Untitled",
    "next_run_at": "2014-11-24T08:29:00Z",
    "owner_id": 2,
    "recurrence_count": null,
    "repeat_by": null,
    "start_at": "2014-10-18T16:29:00Z",
    "status": "enabled",
    "task": {
      "nodes": 2,
      "reuse_cluster": true,
      "terminate_on_idle": true,
      "time_to_idle": 60,
      "jobs": [
        {
          "job_id": "1",
          "variables": {
            "_MAX_COMBINED_SPLIT_SIZE": "67108864",
            "_BYTES_PER_REDUCER": "209715200",
            "_LINE_RECORD_READER_MAX_LENGTH": "1048576",
            "_DEFAULT_TIMEZONE": "''+00:00''",
            "_DEFAULT_PARALLELISM": "0",
            "_SHUFFLE_INPUT_BUFFER_PERCENT": "0.7"
          }
        }
      ]
    },
    "updated_at": "2014-11-24T07:29:21Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/6"
  },
  {
    "created_at": "2014-10-20T12:38:34Z",
    "day_of_week": null,
    "description": "dasdas",
    "end_at": null,
    "execution_count": 0,
    "id": 7,
    "interval_amount": 1,
    "interval_unit": "hours",
    "last_run_at": null,
    "last_run_status": null,
    "name": "Untitled",
    "next_run_at": "2014-11-24T07:34:00Z",
    "owner_id": 2,
    "recurrence_count": null,
    "repeat_by": null,
    "start_at": "2014-10-20T12:34:00Z",
    "status": "disabled",
    "task": {
      "nodes": 2,
      "reuse_cluster": true,
      "terminate_on_idle": true,
      "time_to_idle": 60,
      "jobs": [
        {
          "job_id": "1",
          "variables": {
            "_MAX_COMBINED_SPLIT_SIZE": "67108864",
            "_BYTES_PER_REDUCER": "209715200",
            "_LINE_RECORD_READER_MAX_LENGTH": "1048576",
            "_DEFAULT_TIMEZONE": "''+00:00''",
            "_DEFAULT_PARALLELISM": "0",
            "_SHUFFLE_INPUT_BUFFER_PERCENT": "0.7"
          }
        }
      ]
    },
    "updated_at": "2014-11-24T07:29:29Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/7"
  },
  {
    "created_at": "2014-11-24T07:48:56Z",
    "day_of_week": null,
    "description": "",
    "end_at": null,
    "execution_count": 0,
    "id": 8,
    "interval_amount": 1,
    "interval_unit": "never",
    "last_run_at": null,
    "last_run_status": null,
    "name": "Untitled",
    "next_run_at": "2014-11-24T07:48:00Z",
    "owner_id": 2,
    "recurrence_count": null,
    "repeat_by": null,
    "start_at": "2014-11-24T07:48:00Z",
    "status": "enabled",
    "task": {
      "nodes": 2,
      "reuse_cluster": true,
      "terminate_on_idle": true,
      "time_to_idle": 60,
      "jobs": [
        {
          "job_id": "1",
          "variables": {
            "_MAX_COMBINED_SPLIT_SIZE": "67108864",
            "_BYTES_PER_REDUCER": "209715200",
            "_LINE_RECORD_READER_MAX_LENGTH": "1048576",
            "_DEFAULT_TIMEZONE": "''+00:00''",
            "_DEFAULT_PARALLELISM": "0",
            "_SHUFFLE_INPUT_BUFFER_PERCENT": "0.7"
          }
        }
      ]
    },
    "updated_at": "2014-11-24T07:48:56Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/8"
  }
]
```
