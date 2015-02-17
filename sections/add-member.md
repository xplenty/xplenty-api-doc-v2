## Add Account Member

### Description
This call invites new member to Account with E-mail. Invitation could automatically sets `admin` role for user.

API returns information about user in case of success.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
email|Y| |E-mail of user.
role|N|member|Possible values are `member` or `admin`.

### Request (Curl Call) Syntax
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/members?email=<email>&role=<roleName>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":1,
  "name":"Sample user",
  "email":"sample@example.com",
  "gravatar_email":"sample@example.com",
  "avatar_url":"http://gravatar.com/avatar/20760f72db6d9c7498dc0ba2f6e95fba.png?d=retro&s=140",
  "created_at": "2013-01-17T22:41:21Z",
  "updated_at": "2013-01-17T22:41:21Z",
  "role":"admin",
  "owner":false
}
```
