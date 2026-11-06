## List Audit Event Types

### Description
Returns the event taxonomy the audit log records, grouped by category, with the customer-facing label of each event. Use the ```name``` values as the ```event``` filter of [List Account Audit Events](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-audit-events.md); a category ```name``` followed by ```.*``` selects every event in the category.

Requires the `viewAuditLog` permission and the Audit Log feature enabled on the account.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/audit_event_types" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "actor_types": ["user", "api_key", "mcp", "admin", "system"],
  "categories": [
    {
      "name": "connection",
      "events": [
        { "name": "connection.created", "label": "Connection created" },
        { "name": "connection.updated", "label": "Connection updated" },
        { "name": "connection.deleted", "label": "Connection deleted" }
      ]
    },
    {
      "name": "member",
      "events": [
        { "name": "member.invited", "label": "Member invited" },
        { "name": "member.joined", "label": "Member accepted invitation" },
        { "name": "member.removed", "label": "Member removed" },
        { "name": "member.left", "label": "Member left the account" },
        { "name": "member.role_updated", "label": "Member role changed" },
        { "name": "member.custom_roles_updated", "label": "Member custom roles changed" }
      ]
    },
    {
      "name": "user",
      "events": [
        { "name": "user.signed_in", "label": "Signed in" },
        { "name": "user.sign_in_failed", "label": "Sign-in failed" },
        { "name": "user.signed_out", "label": "Signed out" },
        { "name": "user.password_updated", "label": "Password changed" },
        { "name": "user.mfa_enrolled", "label": "Multi-factor authentication enabled" },
        { "name": "user.mfa_unenrolled", "label": "Multi-factor authentication disabled" }
      ]
    }
  ]
}
```

The full list of categories is ```connection```, ```package```, ```job```, ```schedule```, ```cluster```, ```package_group```, ```connection_group```, ```member```, ```custom_role```, ```account```, ```hook```, ```key```, ```user``` and ```audit_log```.
