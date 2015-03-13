## Update Authenticated User

### Description
This call updates authenticated [user](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/user.md).

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
current_password|Y| |Current password is required to make any changes.
name|N| |The user's name.
email|N| |The user's email. Change of this field requires confirmation.
location|N| |The user's location.
time_zone|N| |The user's time zone.
gravatar_email|N| |The user's gravatar email.
receive_newsletter|N| |Indicates if user subscribed to recieve newsletter
notification_settings:web|N| |Indicates whether web notifications are enabled or not.
notification_settings:email|N| |Indicates whether email notifications are enabled or not.
new_password|N| |New password for authenticated user.

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/user" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "current_password": "password",
    "name": "Sample User",
    "location": "California",
    "email": "test@example.com",
    "notification_settings": { 
      "email": true, 
      "web": true 
    },
    "gravatar_email": "gravater@example.com",
    "time_zone": "UTC",
    "receive_newsletter":true,
    "new_password":"new-password"
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
  "notification_settings": { "email": true, "web": true },
  "gravatar_email":"gravatar@example.com",
  "created_at":"2015-03-04T10:38:05Z",
  "updated_at":"2015-03-04T10:38:05Z",
  "avatar_url":"http://gravatar.com/avatar/675a2c14f074726fc4455ae3bdd1151f.png?d=retro&s=140",
  "last_login":"2015-03-04T10:38:05Z",
  "api_key":"LI4N5OC8RCc53HVWcgQ2h6Ntv46844sl",
  "url":"https://api.xplenty.com/user"
}
```
