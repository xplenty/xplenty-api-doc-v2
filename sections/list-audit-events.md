## List Account Audit Events

### Description
List the account's audit log: who did what in the account, and when. One entry is recorded for every user-visible action — creating, updating or deleting a [connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connection.md), [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md), [schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md), package group, cluster, service hook, log drain or key; changes to which connection groups a package group may use; member invitations, removals and role changes; sign-ins, failed sign-ins and sign-outs; API key and personal access token changes; and jobs started or stopped by a user.

Entries are returned newest first and include an entry for resources that have since been deleted. Secret values (passwords, tokens, keys) are never recorded; a changed secret appears as `"[FILTERED]"`. A connection's password, and where it points (host, port and database), are recorded as changed but without their values, as `"[CHANGED]"`. Recording starts when the Audit Log feature is enabled on the account, and entries are kept for 90 days.

Requires the `viewAuditLog` permission (account owners and admins have it by default; custom roles must be granted it): without it the call returns `403`. With the permission, the call returns `404` when the Audit Log feature is not enabled on the account.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
since|N| |Only entries recorded at or after the given time. UTC, ISO 8601: ```YYYY-MM-DDTHH:MM:SSZ``` or a bare date ```YYYY-MM-DD```.
until|N| |Only entries recorded at or before the given time. Same formats as ```since```; a bare date means the end of that day, so ```until=2026-11-06``` includes all of November 6th.
event|N| |Comma-separated event names (see [List Audit Event Types](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-audit-event-types.md)). A category followed by ```.*``` matches every event in that category, e.g. ```connection.*``` or ```member.*,user.signed_in```. A category is not a name prefix: ```key.*``` matches the ```pgp_key.*```, ```ssh_key.*```, ```api_key.*```, ```personal_token.*``` and ```ai_api_key.*``` events, and ```hook.*``` includes ```log_drain.*```.
actor_type|N| |How the action was performed: ```user``` (dashboard), ```api_key``` (REST API), ```mcp``` (personal access token / MCP client) or ```system```.
actor_id|N| |The id of the user who performed the action (see ```actors``` in [List Audit Event Types](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-audit-event-types.md)).
target_type|N| |The kind of resource acted on, e.g. ```DatabaseConnection```, ```CloudStorageConnection```, ```Job``` (package), ```Schedule```, ```Cluster```, ```Workspace```, ```User```.
target_id|N| |The id of the resource acted on; combine with ```target_type```.
before_id|N| |Return only entries older than the entry with this ```id```: pass the ```id``` of the last entry you received to get the next page. Unlike ```offset```, pages do not shift when new entries are recorded while you page. Returns ```422``` for an ```id``` that is not an entry of this account.
offset|N|0|The number of entries to skip, for paging. Prefer ```before_id```.
limit|N|20|The maximum number of entries to return (20–100). Page through larger result sets with ```before_id```, or follow the ```Link``` header.
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
Link: <https://api.xplenty.com/:account_id/api/audit_events?event=connection.*&since=2026-11-01&before_id=9801>; rel="next"
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
    "target_exists": true,
    "target_subtype": "postgres",
    "workspace_id": null,
    "ip_address": "203.0.113.9",
    "user_agent": "Mozilla/5.0 ...",
    "request_id": "c6c0f3a4-1b7e-4c1a-9f0d-2d5a6e7b8c9d",
    "changes": {
      "name": ["Warehouse", "Warehouse v2"],
      "host": "[CHANGED]"
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
    "target_exists": false,
    "target_subtype": null,
    "workspace_id": null,
    "ip_address": "198.51.100.7",
    "user_agent": "curl/8.4.0",
    "request_id": "0b1f7d2e-5a3c-4e8f-9a1b-7c6d5e4f3a2b",
    "changes": {
      "name": ["Old S3 bucket", null]
    },
    "metadata": null,
    "created_at": "2026-11-05T17:52:10Z"
  }
]
```

### Notes

* ```changes``` is present on update events as ```{"field": [old_value, new_value]}``` for the fields the audit log tracks for that resource. A field whose values are not recorded appears as ```{"field": "[CHANGED]"}``` (a connection's ```password```, ```host```, ```port``` and ```database```), and a settings field records only the names of the keys that changed, e.g. ```{"properties_keys": ["region"]}```. Delete events carry the deleted resource's tracked values as ```{"field": [old_value, null]}```, without the fields whose values are not recorded. Create events carry no ```changes```; the resource's name is in ```target_name```.
* ```target_exists``` is ```true``` while the resource acted on still exists (it is ```false``` once it is deleted, or for a package once it is archived). For connections, ```target_subtype``` is the connection's ```type``` as returned by the connections API, e.g. ```postgres``` or ```s3```; it is ```null``` for other resources and once the connection is deleted.
* ```metadata``` carries event-specific details, e.g. ```{"from": "operator", "to": "admin"}``` on ```member.role_updated```, ```{"reason": "invalid_credentials"}``` on ```user.sign_in_failed```, ```{"added": ["Production"], "removed": ["Staging"], "unrestricted": false}``` on ```package_group.connection_access_updated```, or ```{"package_id": 7, "cluster_id": 3}``` on ```job.run```.
* ```user.sign_in_failed``` has one of two reasons: ```invalid_credentials``` (wrong password) or ```mfa_code_invalid``` (the password was right but the multi-factor code was wrong).
* Sign-in, sign-out, password, MFA and API key events are user-level: they appear in every account the user belongs to that has the Audit Log enabled. ```member.joined``` appears in the account that sent the invitation.
* To export the log as a file, see [Export Account Audit Events](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/export-audit-events.md).
