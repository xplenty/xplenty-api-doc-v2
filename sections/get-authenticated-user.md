## Get Authenticated User

### Description
This call returns the details of the authenticated user.

The details returned for user are:

* **id** - the user's numeric identifier
* **name** - the user's name
* **email** - the user's e-mail
* **time_zone** - the user's time zone
* **location** - the user's location
* **confirmed** - value specifies if user confirmed account or not
* **confirmed_at** - confirmation date and time
* **notifications_count** - number of the user's notifications
* **unread_notifications_count** - number of the user's unread notifications
* **notification_settings** - the user's notification settings
* **receive_newsletter** - value specifies if user subscribed newsletter or not
* **avatar_url** - URL for the user's avatar
* **url** - API url for user
* **created_at** - the date and time the user was created
* **updated_at** - the date and time the user was last updated
* **api_key** - the user's authentication key for API. Returned in response only if user provided password in input parameters.

### Input Parameters
Name|Required?|Default|Description|
current_password|N| |The user's current password. It allows to retrieve information about API key.

### Request (Curl Call) Syntax
```shell
curl -X GET -u api_key: "https://api.xplenty.com/user" -H "Accept: application/vnd.xplenty+json, version=2"
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
  "notification_settings": { "email": true, "web": true },
  "gravatar_email":"user.1@example.com",
  "created_at":"2015-03-04T10:38:05Z",
  "updated_at":"2015-03-04T10:38:05Z",
  "avatar_url":"http://gravatar.com/avatar/675a2c14f074726fc4455ae3bdd1151f.png?d=retro&s=140",
  "url":"/user",
  "last_login":"2015-03-04T10:38:05Z",
  "api_key":"LI4N5OC8RCc53HVWcgQ2h6Ntv46844kl"
}
```
