## Delete Account

### Description
This call deletes the given [account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/account.md). The operation can be executed only by the account owner.

### Notes
* Please note that this action is **irreversible**.

### Input Parameters
The **account ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/accounts/:account_id" \
  -H "Accept: application/vnd.xplenty+json, version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":1,
  "account_id":"xplenty-admin",
  "name":"Xplenty Admin",
  "region":"amazon-web-services::us-east-1",
  "location":null,
  "billing_email":"admin@xplenty.com",
  "gravatar_email":"admin@xplenty.com",
  "avatar_url":"http://gravatar.com/avatar/d41d8cd98f00b204e9800998ecf8427e.png?d=retro&s=140",
  "schedules_count":0,
  "connections_count":0,
  "role":"admin",
  "owner":true,
  "members_count":1,
  "packages_count":0,
  "jobs_count":0,
  "running_jobs_count":0,
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z",
  "url":"https://api.xplenty.com/accounts/xplenty-admin"
}
```
