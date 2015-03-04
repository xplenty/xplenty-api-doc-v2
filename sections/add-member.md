## Add Account Member

### Description
This call adds a new [user](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/user.md) membership to an account. The call sends an invitation to join Xplenty in case the user is not yet a member of Xplenty. 

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
email|Y| |The user's email.
role|N|member|The role to assign to the member. Possible values are `member` or `admin`.

### Request (Curl Call) Syntax
```shell
curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/members" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "email": "sample@example.com",
    "role": "admin"
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
  "gravatar_email":"sample@example.com",
  "avatar_url":"http://gravatar.com/avatar/20760f72db6d9c7498dc0ba2f6e95fba.png?d=retro&s=140",
  "created_at": "2013-01-17T22:41:21Z",
  "updated_at": "2013-01-17T22:41:21Z",
  "role":"admin",
  "owner":false
}
```
