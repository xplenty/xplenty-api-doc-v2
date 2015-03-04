## Get Schedule Information

### Description
Info for an existing [schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md).

### Input Parameters
The **schedule ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/schedules/:schedule_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
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
