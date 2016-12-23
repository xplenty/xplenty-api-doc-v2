## Regenerate user personal authorization tokens

### Description
Regenerates authenticated [user](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/user.md) authorization tokens (API key)

### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/user/regenerate-tokens" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json"
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
  "notification_settings": { 
    "email": true, 
    "web": true 
  },
  "gravatar_email":"gravatar@example.com",
  "created_at":"2015-03-04T10:38:05Z",
  "updated_at":"2015-03-04T10:38:05Z",
  "avatar_url":"http://gravatar.com/avatar/675a2c14f074726fc4455ae3bdd1151f.png?d=retro&s=140",
  "last_login":"2015-03-04T10:38:05Z",
  "api_key":"TI4L5OC8RCc52HveCgq2h6Ntv46444el",
  "url":"https://api.xplenty.com/user"
}
```
