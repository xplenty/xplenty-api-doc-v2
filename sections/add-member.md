## Add Account Member

### Description
Creates a new [member](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/member.md) on an account. The call sends an invitation to join Xplenty in case the user is not yet a user of Xplenty. 

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
email|Y| |The user's email.
name|N| |The user's name. This attribute is considered only when user with specified email does not exist.
role|N|member|The role to assign to the member. Possible values are `member` or `admin`.

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/members" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "email": "sample@example.com",
    "role": "admin",
    "name": "Sample user"
  }'
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
  "display_name": "User Display Name",
  "gravatar_email":"sample@example.com",
  "avatar_url":"http://gravatar.com/avatar/20760f72db6d9c7498dc0ba2f6e95fba.png?d=retro&s=140",
  "created_at": "2013-01-17T22:41:21Z",
  "updated_at": "2013-01-17T22:41:21Z",
  "confirmed_at": "2013-01-17T22:46:21Z",
  "confirmed" : true,
  "role":"admin",
  "owner":false,
  "url": "https://api.xplenty.com/xplenation/api/members/1",
  "html_url": "https://api.xplenty.com/xplenation/settings/members/1"
}
```
