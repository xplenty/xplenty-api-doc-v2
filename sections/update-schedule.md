## Update schedule

### Description
Update an existing [schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md).
Note that you cannot edit start_at date if schedule's execution count is greater than zero.

If you want to use a similar schedule you can clone it using the [clone schedule method](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/clone-schedule.md)

### Input Parameters

| Name                    | Required? | Default      | Description                                                          |
| ----                    | --------- | -------      | -----------                                                          |
| name                    | Y         | Untitled     | Name to assign to the new schedule                                   |
| status                  | N         | disabled     | Initial status of the schedule                                       |
| start_at                | Y         | Current time | Time when the task will first trigger                                |
| description             | N         | blank        | Description to assign to the new schedule                            |
| interval_amount         | Y         | 1            | Number of interval units between schedule's task executions          |
| interval_unit           | Y         | hours        | Schedule's interval unit. Possible values are: `minutes`, `hours`, `days`, `weeks`, `years`.|
| reuse_cluster_strategy  | N         | any          | Strategy of re-using cluster. Possible values are: `none`, `from_master`, `any`|
| task[nodes]             | N         | 2            | The number of compute nodes for the task will exacute on             |
| task[terminate_on_idle] | N         | true         | Indicates if the cluster will terminate automatically                 |
| task[time_to_idle]      | N         | 60           | Time after which the cluster will terminate                          | 
| task[packages]  | N         | blank        | Array of package ids with variables                                        |

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/:account_id/api/schedules/:schedule_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name":"My Schedule",
    "status":"enabled",
    "start_at":"2014-09-25T08:33:00Z",
    "description":"A monthly schedule",
    "interval_amount":30,
    "interval_unit":"days",
    "reuse_cluster_strategy":"any",
    "task": {
      "nodes":4,
      "terminate_on_idle":true,
      "time_to_idle":60,
      "packages":[
        {
          "package_id": "1234",
          "variables": {
            "today": "'val1'",
            "yesterday": "'val2'"
          }
        },{
          "package_id": "3456",
          "variables": {
            "today": "'val3'",
            "yesterday": "'val4'"
          }
        }
      ]
    }
  }'
```

You can add multiple variables for a package and multiple packages. 

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "created_at": "2014-09-25T08:48:51Z",
  "name": "My Schedule",
  "description": "A monthly schedule",
  "execution_count": 0,
  "id": 2,
  "interval_amount": 30,
  "interval_unit": "days",
  "last_run_at": "2014-09-25T08:48:00Z",
  "last_run_status": null,
  "next_run_at": "2014-09-25T08:48:00Z",
  "owner_id": 1,
  "start_at": "2014-09-25T08:48:00Z",
  "status": "enabled",
  "reuse_cluster_strategy":"any",
  "task": {
    "nodes": 4,
    "terminate_on_idle": true,
    "time_to_idle": 60,
    "packages":[
      {
        "package_id": "1234",
        "variables": {
          "today": "'val1'",
          "yesterday": "'val2'"
        }
      },{
        "package_id": "3456",
        "variables": {
          "today": "'val3'",
          "yesterday": "'val4'"
        }
      }
    ]
  },
  "updated_at": "2014-10-29T14:22:05Z",
  "url": "https://api.xplenty.com/xplenation/api/schedules/2"
}
```
