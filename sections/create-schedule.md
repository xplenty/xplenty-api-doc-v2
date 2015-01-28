## Create Schedule

### Description
This call creates a new schedule. A schedule executes packages periodically starting at a specified date and time. The packages will be executed as scheduled, using an existing cluster that fits the scheduled cluster size or if one doesn't exist, a cluster will be provisioned automatically with the number of specified nodes. 

A successful call returns the following details for the the schedule:

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
    * **years**
* **task**
* **last_run_at** the date and time that schedule's task ran last
* **last_run_status** status of the last execution of the schedule's task
* **execution_count** number of times the schedule has run
* **created_at** the date and time the schedule was created
* **updated_at** the date and time the schedule was updated
* **url** the schedule resource ID

### Notes
* This call only triggers schedule creation, and therefore it returns the "disabled" status. To enable a schedule you need to change its status to "enabled" using [update schedule's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/update-schedule-information.md)
You can verify that a schedule has initialized successfully by [retrieving the schedule's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-schedule-information.md) and checking for the "enabled" status.
* You must save the chedule ID value returned in the response "id" field. You will use the value to refer to this schedule in subsequent API calls.

### Input Parameters
| Name                    | Required? | Default      | Description                                                          |
| ----                    | --------- | -------      | -----------                                                          |
| name                    | Y         | Untitled     | Name to assign to the new schedule                                   |
| status                  | N         | disabled     | Initial status of the schedule                                       |
| start_at                | Y         | Current time | Time when the task will first trigger                                |
| description             | N         | blank        | Description to assign to the new schedule                            |
| interval_amount         | Y         | 1            | Number of interval units between schedule's task executions          |
| interval_unit           | Y         | hours        | Schedule's interval unit                                             |
| task[nodes]             | N         | 2            | The number of compute nodes for the task to execute on             |
| task[terminate_on_idle] | N         | true         | Indicates if the cluster will terminate automatically                 |
| task[time_to_idle]      | N         | 60           | Time after which the cluster will terminate                          |
| task[packages]  | N         | blank        | Array of package ids with variables                                        |

### Request (Curl Call) Example
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules"
    -d "schedule[name]=<name>"
    -d "schedule[status]=enabled"
    -d "schedule[start_at]=<start_at>"
    -d "schedule[description]=<description>"
    -d "schedule[interval_amount]=<interval_amount>"
    -d "schedule[interval_unit]=<interval_unit>"
    -d "schedule[task][nodes]=<nodes>"
    -d "schedule[task][terminate_on_idle]=<terminate_on_idle>"
    -d "schedule[task][time_to_idle]=<time_to_idle>"
    -d task[packages][<index>][package_id] = <package_id>
    -d task[packages][<index>][variables][<var_name>] = variable value
```
Add multiple variables for a package and multiple packages. The index is 0 for the first package and incremented for each additional package.

### Response Example
```json
{
  "created_at": "2014-09-25T08:48:51Z",
  "description": "dsada",
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
