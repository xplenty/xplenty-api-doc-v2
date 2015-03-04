## Get Authenticated User

### Description
Info for the authenticated user.

### Input Parameters
Name|Required?|Default|Description|
current_password|N| |The user's current password. It allows to retrieve information about API key.

### Request (Curl Call) Syntax
```shell
curl -X GET -u api_key: "https://api.xplenty.com/user" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "current_password":"password"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":1,
  "name":"Test User 1",
  "email":"test.user@example.com",
  "confirmed":true,
  "confirmed_at":"2015-03-04T10:38:03Z",
  "receive_newsletter":false,
  "location":null,
  "time_zone":"UTC",
  "notifications_count":0,
  "unread_notifications_count":0,
  "gravatar_email":"gravatar@example.com",
  "created_at":"2015-03-04T10:38:05Z",
  "updated_at":"2015-03-04T10:38:05Z",
  "avatar_url":"http://gravatar.com/avatar/675a2c14f074726fc4455ae3bdd1151f.png?d=retro&s=140",
  "last_login":"2015-03-04T10:38:05Z",
  "api_key":"LI4N5OC8RCc53HVWcgQ2h6Ntv46844sl",
  "url":"https://api.xplenty.com/user"
}
```
