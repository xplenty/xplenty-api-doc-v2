## List Account Audit Events

### Description
List the account's audit log: who did what in the account, and when. One entry is recorded for every user-visible action — creating, updating or deleting a [connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connection.md), [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md), [schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md), package group, cluster, service hook, log drain or key; member invitations, removals and role changes; sign-ins, failed sign-ins and sign-outs; API key and personal access token changes; and jobs started or stopped by a user.

Entries are returned newest first and include an entry for resources that have since been deleted. Secret values (passwords, tokens, keys) are never recorded; a changed secret appears as `"[FILTERED]"`. Entries are kept for 90 days.

Requires the `viewAuditLog` permission (account owners and admins have it by default; custom roles must be granted it) and the Audit Log feature enabled on the account (otherwise the call returns `404`).

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
since|N| |Only entries recorded at or after the given time. UTC, ISO 8601: ```YYYY-MM-DDTHH:MM:SSZ``` or a bare date ```YYYY-MM-DD```.
until|N| |Only entries recorded at or before the given time. Same formats as ```since```; a bare date means the end of that day, so ```until=2026-11-06``` includes all of November 6th.
event|N| |Comma-separated event names (see [List Audit Event Types](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-audit-event-types.md)). A category followed by ```.*``` matches every event in it, e.g. ```connection.*``` or ```member.*,user.signed_in```.
actor_type|N| |Who performed the action: ```user``` (dashboard), ```api_key``` (REST API), ```mcp``` (personal access token / MCP client), ```admin``` (Integrate.io staff) or ```system```.
actor_id|N| |The id of the user who performed the action.
target_type|N| |The kind of resource acted on, e.g. ```DatabaseConnection```, ```CloudStorageConnection```, ```Job``` (package), ```Schedule```, ```Cluster```, ```Workspace```, ```User```.
target_id|N| |The id of the resource acted on; combine with ```target_type```.
offset|N|0|The number of entries to skip, for paging.
limit|N|20|The maximum number of entries to return (20–100). Page through larger result sets with ```offset``` or the ```Link``` header.
include_count|N|false|When ```true```, the response carries an ```X-Total-Count``` header with the number of entries matching the filters.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/audit_events?event=connection.*&since=2026-11-01" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
Link: <https://api.xplenty.com/:account_id/api/audit_events?event=connection.*&since=2026-11-01&offset=20>; rel="next"
```

```json
[
  {
    "id": 9812,
    "event": "connection.updated",
    "label": "Connection updated",
    "actor_type": "user",
    "actor_id": 42,
    "actor_email": "jane@example.com",
    "target_type": "DatabaseConnection",
    "target_id": 17,
    "target_name": "Warehouse",
    "workspace_id": null,
    "ip_address": "203.0.113.9",
    "user_agent": "Mozilla/5.0 ...",
    "request_id": "c6c0f3a4-1b7e-4c1a-9f0d-2d5a6e7b8c9d",
    "changes": {
      "name": ["Warehouse", "Warehouse v2"],
      "host": ["db.internal", "db2.internal"],
      "password": "[FILTERED]"
    },
    "metadata": null,
    "created_at": "2026-11-06T09:03:44Z"
  },
  {
    "id": 9801,
    "event": "connection.deleted",
    "label": "Connection deleted",
    "actor_type": "api_key",
    "actor_id": 42,
    "actor_email": "jane@example.com",
    "target_type": "CloudStorageConnection",
    "target_id": 12,
    "target_name": "Old S3 bucket",
    "workspace_id": null,
    "ip_address": "198.51.100.7",
    "user_agent": "curl/8.4.0",
    "request_id": "0b1f7d2e-5a3c-4e8f-9a1b-7c6d5e4f3a2b",
    "changes": null,
    "metadata": null,
    "created_at": "2026-11-05T17:52:10Z"
  }
]
```

### Notes

* ```changes``` is present on update events as ```{"field": [old_value, new_value]}``` for the fields the audit log tracks for that resource. Create and delete events carry no ```changes```; the resource's name is in ```target_name```.
* ```metadata``` carries event-specific details, e.g. ```{"from": "operator", "to": "admin"}``` on ```member.role_updated```, ```{"reason": "invalid_credentials"}``` on ```user.sign_in_failed```, or ```{"package_id": 7, "cluster_id": 3}``` on ```job.run```.
* Sign-in, sign-out, password, MFA and API key events are user-level: they appear in every account the user belongs to. Integrate.io staff sign-ins are not recorded.
* To export the log as a file, see [Export Account Audit Events](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/export-audit-events.md).
