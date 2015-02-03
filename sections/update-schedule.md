## Update schedule

### Description
This call updates the given schedule.
Note that you cannot edit start_at date if schedule's execution count is greater than zero.

If you want to use a similar schedule you can clone it using the [clone schedule method](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/clone-schedule.md)

A successful call returns the following details for the schedule after the changes.

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

| Name                    | Required? | Default      | Description                                                          |
| ----                    | --------- | -------      | -----------                                                          |
| name                    | Y         | Untitled     | Name to assign to the new schedule                                   |
| status                  | N         | disabled     | Initial status of the schedule                                       |
| start_at                | Y         | Current time | Time when the task will first trigger                                |
| description             | N         | blank        | Description to assign to the new schedule                            |
| interval_amount         | Y         | 1            | Number of interval units between schedule's task executions          |
| interval_unit           | Y         | hours        | Schedule's interval unit                                             |
| task[nodes]             | N         | 2            | The number of compute nodes for the task will exacute on             |
| task[terminate_on_idle] | N         | true         | Indicates if the cluster will terminate automatically                 |
| task[time_to_idle]      | N         | 60           | Time after which the cluster will terminate                          | 
| task[packages]  | N         | blank        | Array of package ids with variables                                        |

### Request (Curl Call) Syntax
```shell
curl -X PUT -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules/<scheduleID>"
  -d "schedule[name]=<name>"
  -d "schedule[description]=<description>"
  -d "schedule[status]=enabled"
  -d "schedule[start_at]=<start_at>"
  -d "schedule[interval_amount]=<interval_amount>"
  -d "schedule[interval_unit]=<interval_unit>"
  -d "schedule[task][nodes]=<nodes>"
  -d "schedule[task][terminate_on_idle]=<terminate_on_idle>"
  -d "schedule[task][time_to_idle]=<time_to_idle>"
  -d "schedule[task][packages][<index>][package_id] = <package_id>"
  -d "schedule[task][packages][<index>][variables][<var_name>] = variable value"
```

Add multiple variables for a package and multiple packages. The index is 0 for the first package and incremented for each additional package. For example:
```shell
   -d "schedule[task][packages][0][package_id] = 1234"
   -d "schedule[task][packages][0][variables][today] = 'val1'"
   -d "schedule[task][packages][0][variables][yesterday] = 'val2'"
   -d "schedule[task][packages][1][package_id] = 3456"
   -d "schedule[task][packages][1][variables][today] = 'val3'"
   -d "schedule[task][packages][1][variables][yesterday] = 'val4'"
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
