## Clone schedule

### Description
Clone an existing [schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md).

### Input Parameters

| Name | Required? | Default | Description                          |
| ---- | --------- | ------- | -----------                          |
| id   | Y         | blank   | id of the schedule you want to clone |

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/schedules/:schedule_id/clone" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

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
  "name": "Copy of Untitled",
  "next_run_at": "2014-12-02T08:33:00Z",
  "owner_id": 1,
  "start_at": "2014-09-25T08:33:00Z",
  "status": "enabled",
  "task": {
    "nodes": 3,
    "packages": [
      {
        "package_id": "1",
        "variables": {
          "_MAX_COMBINED_SPLIT_SIZE": "67108864",
          "_BYTES_PER_REDUCER": "209715200",
          "_LINE_RECORD_READER_MAX_LENGTH": "1024000",
          "_DEFAULT_TIMEZONE": "'+00:00'",
          "_DEFAULT_PARALLELISM": "0",
          "_SHUFFLE_INPUT_BUFFER_PERCENT": "0.7"
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
