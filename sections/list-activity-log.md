## List Account Activity Log

### Description
List the account-wide, read-only compliance/audit activity log: who changed a [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md), [schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md), or [connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connection.md) on this account, what changed, and when -- including entries for resources that have since been deleted.

Optionally, you can supply the input parameters to filter the log by resource type, the user who made the change, and/or a date range, and to page through a large history.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
resource_type|N| |Possible values are ```package```, ```schedule```, or ```connection```. The call will return only activity for the given resource type, or activity for all three if omitted.
user|N| |The email address of the user who made the change. The call will return only activity performed by that user.
from|N| |The activity list will only contain entries at or after the given time. Accepts either a date (```YYYY-MM-DD```) or a full UTC timestamp in ISO 8601 format, e.g. ```2026-07-01``` or ```2026-07-01T00:00:00Z```.
to|N| |The activity list will only contain entries at or before the given time. Same accepted formats as ```from```. A bare date is treated as the end of that day, so ```to=2026-08-19``` includes all of August 19th.
offset|N|0|The number of entries to skip, for paging through a large result set.
limit|N|20|The maximum number of entries to return. Capped at 100 per request; page through larger result sets with ```offset```.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/activity_logs?resource_type=connection&from=2026-07-01" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "entries": [
    {
      "resource_type": "schedule",
      "resource_id": 42,
      "resource_name": "Daily sync",
      "action": "update",
      "user": "jane@example.com",
      "created_at": "2026-08-19T17:52:10Z",
      "changes": {
        "status": ["disabled", "enabled"]
      }
    },
    {
      "resource_type": "connection",
      "resource_id": 17,
      "resource_name": "Old S3 bucket",
      "action": "destroy",
      "user": "jane@example.com",
      "created_at": "2026-08-18T09:03:44Z",
      "changes": {
        "name": ["Old S3 bucket", null],
        "bucket": ["archive-bucket", null]
      }
    }
  ],
  "total_count": 214,
  "offset": 0,
  "limit": 20
}
```

### Notes

* Unlike most list endpoints in this API, pagination metadata (```total_count```, ```offset```, ```limit```) is returned in the response body rather than a ```Link``` header, since a single page mixes entries from three underlying sources (packages, schedules, connections) sorted together by time.
* ```action``` is one of ```create```, ```update```, or ```destroy```. For ```create```, ```changes``` shows every field as ```[null, value]```; for ```destroy```, every field as ```[value, null]``` (the resource's last known state); for ```update```, only the fields that actually changed, as ```[old_value, new_value]```.
* An entry for a deleted resource still includes its ```resource_name``` and full history, recovered from the change record itself since the live resource no longer exists.
* Fields that look sensitive (```encrypted_*```, anything matching ```*password*```/```*secret*```/```*token*```, or IV/salt columns) are always stripped from ```changes```, even though the underlying data is ciphertext rather than plaintext.
* Requires the same account-management permission level as other account-settings pages (not a dedicated permission).
