## Export Account Audit Events

### Description
Download the account's audit log as a CSV file. Accepts the same filters as [List Account Audit Events](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-audit-events.md) (```since```, ```until```, ```event```, ```actor_type```, ```actor_id```, ```target_type```, ```target_id```); ```offset``` and ```limit``` are ignored and every matching entry is returned, newest first.

An export is capped at 10,000 entries. Above the cap the call returns ```422``` and asks you to narrow the date range or filters. The export itself is recorded in the audit log as an ```audit_log.exported``` event.

Requires the `viewAuditLog` permission (otherwise `403`) and the Audit Log feature enabled on the account (otherwise `404`).

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/audit_events/export?since=2026-10-01&until=2026-10-31" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -o audit-log-october.csv
```

### Response Example
```HTTP
HTTP/1.1 200 OK
Content-Type: text/csv; charset=utf-8
Content-Disposition: attachment; filename="audit-log-myaccount-20261106T090344Z.csv"
```

```csv
id,timestamp_utc,event,event_label,actor_type,actor_id,actor_email,target_type,target_id,target_name,workspace_id,ip_address,user_agent,request_id,changes,metadata
9812,2026-11-06T09:03:44Z,connection.updated,Connection updated,user,42,jane@example.com,DatabaseConnection,17,Warehouse,,203.0.113.9,Mozilla/5.0 ...,c6c0f3a4-1b7e-4c1a-9f0d-2d5a6e7b8c9d,"{""name"":[""Warehouse"",""Warehouse v2""]}",
9801,2026-11-05T17:52:10Z,connection.deleted,Connection deleted,api_key,42,jane@example.com,CloudStorageConnection,12,Old S3 bucket,,198.51.100.7,curl/8.4.0,0b1f7d2e-5a3c-4e8f-9a1b-7c6d5e4f3a2b,,
```

The ```changes``` and ```metadata``` columns hold the same JSON objects the list call returns, serialized as strings.

So that a spreadsheet never runs a cell as a formula, any cell that starts with ```=```, ```+```, ```-```, ```@```, a tab or a carriage return is prefixed with a single quote (```'```). A connection named ```=SUM(A1)``` is exported as ```'=SUM(A1)```.
