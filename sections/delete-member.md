## Delete Account Member

### Description
This call deletes the [member](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/user.md) from the account. It does not remove the user, just the account membership.

### Input Parameters
The **user ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json, version=2" -u api_key: "https://api.xplenty.com/:account_id/api/members/<userID>"
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
  "owner":true
}
```
