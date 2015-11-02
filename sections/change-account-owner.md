## Update Account

### Description
This call changes owner of the [account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/account.md). Only current owner can perform this action.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
account_id|Y| |The account string identifier. Account ID provided in URL identifies account but account_id parameter passed in JSON allows to change ID.
user_id|Y| |The ID of user who will be a new owner

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/accounts/:account_id/change_owner" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{ "user_id": 1 }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":"1",
  "name":"Sample Admin",
  "uname": "u_1",
  "account_id":"sample-admin",
  "region":"amazon-web-services::us-east-1",
  "location":"California",
  "billing_email":"billing@example.com",
  "gravatar_email":"gravater@example.com",
  "avatar_url":"http://gravatar.com/avatar/d24d8cd923f00b204e9800998ecf8427e.png?d=retro&s=140",
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z",
  "schedules_count":0,
  "connections_count":2,
  "role":"member",
  "owner":false,
  "members_count":3,
  "packages_count":0,
  "jobs_count":1,
  "running_jobs_count":0,
  "url":"https://api.xplenty.com/accounts/sample-admin"
}
```
