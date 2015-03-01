## Set Member's Role

### Description
This call sets the Account [member's](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/user.md) role to either: `member` or `admin`. 

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
user_id|Y| |ID of user, must be supplied at the end of the request URL.
role|Y| |Possible values are `member` or `admin`.

### Request (Curl Call) Syntax
```shell
curl -X PUT -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/members/<userID>?role=<roleName>" -d ''
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
  "avatar_url":"http://gravatar.com/avatar/20760f72db6d9c7498dc0ba2f6e95fba.png?d=retro&s=140",
  "created_at": "2013-01-17T22:41:21Z",
  "updated_at": "2013-01-17T22:41:21Z",
  "role":"admin",
  "owner":true
}
```
