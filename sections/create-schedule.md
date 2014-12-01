## Create Schedule

### Description
This call creates a new schedule. Schedule is a

A successful call returns the following details for the the schedule:
<!-- #TODO -->

### Notes
* This call only triggers schedule creation, and therefore it returns the "disabled" status. To enable a schedule you need to chagne its status to "enabled" using [update schedule's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/update-schedule-information.md)
You can verify that a schedule has initialized successfully by [retrieving the shcedule's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-schedule-information.md) and checking for the "enabled" status.
* You must save the chedule ID value returned in the response "id" field. You will use the value to refer to this schedule in subsequent API calls.

### Input Parameters
<!-- #TODO -->

### Request (Curl Call) Example
```shell
<!-- #TODO -->
```

### Response Example
```json
<!-- #TODO -->
```
