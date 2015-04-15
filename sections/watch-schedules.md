# Watch Schedule

## Description
You can choose to "watch" schedule items that you or other users have created.
If you're watching an item, you'll receive notifications on important updates.

**For schedule items**, you'll receive notifications when the schedule reaches the "enabled", "disabled" statuses.

The notifications can be sent as email messages, or as messages which you can view in the Xplenty web application.
You can change the method of notification for your user in [notification settings page](https://app.xplenty.com/settings/notifications).

Users can add or remove themselves from the watcher list of specific items, and can retrieve the list of watchers for a specific item.
Below are descriptions of the API calls that add, delete and retrieve watchers for schedules.

## Notes
By default, the user who created a schedule item will be a watcher of that item.

## Watch Schedule
This call adds the calling user as a watcher of the specified schedule.

### Input Parameters
* **schedule_id** - the ID of the schedule to watch

### Request (Curl Call)
```shell
$ curl -X POST -u api_key: 'https://api.xplenty.com/:account_id/api/schedules/:schedule_id/watchers' \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "created_at":"2013-04-09T11:19:20+03:00",
  "schedule_url":"https://api.xplenty.com/xplenation/api/schedules/370"
}
```

## Stop Watching Schedule
This call removes the calling user from the watcher list of the specified schedule.

### Input Parameters
* **schedule_id** - the ID of the schedule to stop watching

### Request (Curl Call)
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/schedules/:schedule_id/watchers" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response
```HTTP
HTTP/1.1 204 No Content
```

## Get Schedule Watchers
This call retrieves the list of users watching the specified schedule.

### Input Parameters
* **schedule_id** - the ID of the schedule to whose watchers you want to retrieve

### Request (Curl Call)
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/schedules/:schedule_id/watchers" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id":1,
    "display_name":"Xplenty"
  }
]
```
