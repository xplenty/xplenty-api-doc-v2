## Delete Schedule

### Description
This call removes the given schedule.

Use this call when the schedule is no longer needed.

A successful call returns empty body and a status of 204.

### Notes
* This call removes the schedule all together - contrary to some other resources this one **won't** be archived / updated.
You can verify that a schedule has been removed successfully by [retrieving the schedules's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-schedule-information.md).

### Input Parameters
The **schedule resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules/<scheduleID>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "created_at": "2014-09-25T08:48:51Z",
  "description": "My daily schedule",
  "execution_count": 0,
  "id": 2,
  "interval_amount": 34,
  "interval_unit": "days",
  "last_run_at": null,
  "last_run_status": null,
  "name": "Untitled",
  "next_run_at": "2014-12-02T08:33:00Z",
  "owner_id": 1,
  "start_at": "2014-09-25T08:33:00Z",
  "status": "enabled",
  "task": {
    "nodes": 3,
    "packages": [
      {
        "package_id": "1234",
        "variables": {
          "today": "'val1'",
          "yesterday": "'val2'"
        }
      }
      ,      
      {
        "package_id": "3456",
        "variables": {
          "today": "'val3'",
          "yesterday": "'val4'"
        }
      }
    ],
    "terminate_on_idle": true,
    "time_to_idle": 60
  },
  "updated_at": "2014-10-29T14:22:05Z",
  "url": "https://api.xplenty.com/xplenation/api/schedules/2"
}
```
