## Update schedule

### Description
This call updates the given schedule.
Note that you cannot edit start_at date if schedule's execution count is greater than zero.

If you want to use similar schedule you can clone it using the [clone schedule method](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/clone-schedule.md)

A successful call returns the following details for the schedule after the changes.


* **id** the numeric schedule ID
* **owner_id** the numeric user id of the package owner
* **name** the name given to the schedule upon creation
* **status** the schdule's status. Possible values are:
    * **enabled**
    * **disabled**
* **task**
* **start_at** the date and time when the schedule will run or did run for the first time
* **end_at** the date and time after which no more jobs will be scheduled
* **recurrence_count** number of times the schedule is going to be executed
* **next_run_at** the date and time the schedule's task will run next time
* **last_run_at** the date and time when schedule's task run last time
* **last_run_status** status of the execution of the schedule's task
* **execution_count** number of times the schedule has ran
* **created_at** the date and time the schedule was created
* **updated_at** the date and time the schedule was updated
* **description** the description given to the schedule upon creation
* **interval_amount** numer of interval units between schedule's task executions
* **interval_unit** Possible values are:
    * **never**
    * **seconds**
    * **minutes**
    * **hours**
    * **days**
    * **weeks**
    * **months**
* **repeat_by** Applies only when **interval_unit** is set to "months". Possible values are:
    * **day_of_the_month** it will trigger on the day of the month when the task has ran for the first time. For months that have fewer days, this task will run on the last day of the month.
    * **day_of_the_week** it will trigger in the first 7 days of the month, on the same day of the week that the task has ran for the first time.
* **day_of_week** day of the week on which the schedule will trigger. Applies only when **interval_unit** is set to weeks. Possible values are integers between: 0 and 6.
    * **0** => Sun
    * **1** => Mon
    * **2** => Tue
    * **3** => Wed
    * **4** => Thu
    * **5** => Fri
    * **6** => Sat
* **url** the schedule resource ID

### Input Parameters

| Name                    | Required? | Default      | Description                                                          |
| ----                    | --------- | -------      | -----------                                                          |
| name                    | Y         | Untitled     | Name to assign to the new schedule                                   |
| status                  | N         | disabled     | Initial status of the schedule                                       |
| start_at                | Y         | Current time | Time when the task will first trigger                                |
| end_at                  | N         | blank        | Time after which schedule will no longer trigger                     |
| recurrence_count        | N         | blank        | Number of times the schedule is going to be executed                 |
| description             | N         | blank        | Description to assign to the new schedule                            |
| interval_amount         | Y         | 1            | Number of interval units between schedule's task executions          |
| interval_unit           | Y         | hours        | Schedule's interval unit                                             |
| repeat_by               | N         | blank        | Indicates repeat day for monthly tasks                               |
| day_of_week             | N         | blank        | Day of the week when the task will be executed (for weekly interval) |
| task[nodes]             | N         | 2            | The number of compute nodes for the task will exacute on             |
| task[terminate_on_idle] | N         | true         | Indicates if the cluster will termiate automatically                 |
| task[time_to_idle]      | N         | 60           | Time after which the cluster will terminate                          |
| task[reuse_cluster]     | N         | true         | #TODO is it always true now ?                                        |
| task[job_ids]           | N         | blank        | Array of job ids for the task                                        |

### Request (Curl Call) Syntax
```shell
    curl -X PUT -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules/<scheduleID>"
      -d "schedule[name]=<name>"
      -d "schedule[status]=enabled"
      -d "schedule[start_at]=<start_at>"
      -d "schedule[end_at]=<end_at>"
      -d "schedule[recurrence_count]=<recurrece_count>"
      -d "schedule[description]=<description>"
      -d "schedule[interval_amount]=<interval_amount>"
      -d "schedule[interval_unit]=<interval_unit>"
      -d "schedule[repeat_by]=<repeat_by>"
      -d "schedule[day_of_week]=<day_of_week>"
      -d "schedule[task][nodes]=<nodes>"
      -d "schedule[task][terminate_on_idle]=<terminate_on_idle>"
      -d "schedule[task][time_to_idle]=<time_to_idle>"
      -d "schedule[task][reuse_cluster]=<reuse_cluster>"
      -d "schedule[task][job_ids]=<job_ids>"
```

### Response Example
```json
    {
      "created_at": "2014-09-25T08:48:51Z",
      "day_of_week": null,
      "description": "dsada",
      "end_at": "2014-09-25T10:45:00Z",
      "execution_count": 0,
      "id": 2,
      "interval_amount": 34,
      "interval_unit": "days",
      "last_run_at": null,
      "last_run_status": null,
      "name": "Untitled",
      "next_run_at": "2014-12-02T08:33:00Z",
      "owner_id": 1,
      "recurrence_count": 2,
      "repeat_by": null,
      "start_at": "2014-09-25T08:33:00Z",
      "status": "enabled",
      "task": {
        "nodes": 3,
        "jobs": [
          {
            "job_id": "1",
            "variables": {
              "_MAX_COMBINED_SPLIT_SIZE": "67108864",
              "_BYTES_PER_REDUCER": "209715200",
              "_LINE_RECORD_READER_MAX_LENGTH": "1024000",
              "_DEFAULT_TIMEZONE": "+00:00",
              "_DEFAULT_PARALLELISM": "0",
              "_SHUFFLE_INPUT_BUFFER_PERCENT": "0.7"
            }
          }
        ],
        "reuse_cluster": true,
        "terminate_on_idle": true,
        "time_to_idle": 60
      },
      "updated_at": "2014-10-29T14:22:05Z",
      "url": "https://api.xplenty.com/xplenation/api/schedules/2"
    }
```
