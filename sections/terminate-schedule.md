## Terminate Schedule

### Description
This call removes the given schedule.

Use this call when the schedule is no longer needed.

A successful call returns empty body and a status of 204.

### Notes
* This call removes the schedule all together - contrary to some other resources this one **won't** be archived / updated.
You can verify that a schedule has been removed successfully by [retrieving the schedules's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-schedule-information.md) and checking for the the HTTP code - it should give you a 404

### Input Parameters
The **schedule resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
    curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules/<scheduleID>"
```

### Response Example
``` HTTP
    204 No Content
```
