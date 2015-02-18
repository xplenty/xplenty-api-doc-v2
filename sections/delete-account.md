## Delete Account Connection

### Description
This call deletes account. Operation can be execute by owner only.

### Notes
* Please note that this action is **irreversible**.

### Input Parameters
The **connection ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/accounts/<accountID>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":"xplenty-admin",
  "name":"Xplenty Admin",
  "region":"amazon-web-services::us-east-1",
  "location":null,
  "billing_email":"admin@xplenty.com",
  "gravatar_email":"admin@xplenty.com",
  "avatar_url":"http://gravatar.com/avatar/d41d8cd98f00b204e9800998ecf8427e.png?d=retro&s=140",
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z"
}
```
