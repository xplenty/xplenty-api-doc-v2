## Get Schedule Information

### Description
The call returns information for a schedule with the given schedule ID.

The details returned for the schedule are:

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
The **schedule ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules/<scheduleID>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
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
}
```
