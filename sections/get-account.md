## Get Account Information

### Description
Information about active [account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/account.md).
The authenticated user must be a member of this account (with either admin or member role).

### Input Parameters
The **account resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/accounts/:account_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":1,
  "account_id":"sample-account-1",
  "name":"Xplenty Admin",
  "region":"amazon-web-services::us-east-1",
  "location":null,
  "billing_email":"billing@example.com",
  "gravatar_email":"gravatar@example.com",
  "avatar_url":"http://gravatar.com/avatar/d41d8cd98f00b204e9800998ecf8427e.png?d=retro&s=140",
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z",
  "schedules_count":0,
  "connections_count":2,
  "role":"admin",
  "owner":true,
  "members_count":2,
  "packages_count":51,
  "jobs_count":0,
  "running_jobs_count":0,
  "url":"https://api.xplenty.com/accounts/sample-account-1"
}
```