## Create Schedule

### Description
This call creates a new [schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md). A schedule executes packages periodically starting at a specified date and time. The packages will be executed as scheduled, using an existing cluster that fits the scheduled cluster size or if one doesn't exist, a cluster will be provisioned automatically with the number of specified nodes. 

### Notes
* This call only triggers schedule creation, and therefore it returns the "disabled" status. To enable a schedule you need to change its status to "enabled" using [update schedule's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-schedule-information.md)
You can verify that a schedule has initialized successfully by [retrieving the schedule's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-schedule-information.md) and checking for the "enabled" status.
* You must save the schedule ID value returned in the response "id" field. You will use the value to refer to this schedule in subsequent API calls.

### Input Parameters
| Name                    | Required? | Default      | Description                                                          |
| ----                    | --------- | -------      | -----------                                                          |
| name                    | Y         | Untitled     | Name to assign to the new schedule                                   |
| status                  | N         | disabled     | Initial status of the schedule                                       |
| start_at                | Y         | Current time | Time when the task will first trigger                                |
| description             | N         | blank        | Description to assign to the new schedule                            |
| interval_amount         | Y         | 1            | Number of interval units between schedule's task executions          |
| interval_unit           | Y         | hours        | Schedule's interval unit. Possible values are: `minutes`, `hours`, `days`, `weeks`, `years`.|
| task[nodes]             | N         | 2            | The number of compute nodes for the task to execute on             |
| task[terminate_on_idle] | N         | true         | Indicates if the cluster will terminate automatically                 |
| task[time_to_idle]      | N         | 60           | Time after which the cluster will terminate                          |
| task[packages]  |  N         | blank        | Array of package ids with variables                                        |

### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/schedules" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name":"schedule name",
	"status":"enabled",
	"start_at":"2014-09-25T08:33:00Z",
	"description":"schedule description",
	"interval_amount":30,
	"interval_unit":"days",
	"task": {
      "nodes":4,
	  "terminate_on_idle":true,
	  "time_to_idle":60,
	  "packages": [
      {
        "package_id": "1234",
        "variables": {
          "today": "'val1'",
          "yesterday": "'val2'"
        }
      },  
	  {
        "package_id": "3456",
        "variables": {
          "today": "'val3'",
          "yesterday": "'val4'"
        }
      }
    ],
  }'
```
You can add multiple variables for a package and multiple packages.

### Response Example
```HTTP
HTTP/1.1 201 Created
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
