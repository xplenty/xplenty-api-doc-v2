## Get Account Member Information

### Description
Information about [member](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/member.md) of the account.

### Input Parameters
The **account ID** and **member ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/members/:member_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":1,
  "name":"Xplenty Admin",
  "email":"admin@example.com",
  "gravatar_email":"admin@example.com",
  "avatar_url":"https://xplenty.com/path/to/avatar.png",
  "created_at": "2013-01-17T22:41:21Z",
  "updated_at": "2013-01-17T22:41:21Z",
  "role":"admin",
  "owner":true,
  "url": "https://api.xplenty.com/xplenation/api/members/1",
  "html_url": "https://xplenty.com/xplenation/members/1"
}
```
