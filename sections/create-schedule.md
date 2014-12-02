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

### Request (Curl Call) Example
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules"
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
