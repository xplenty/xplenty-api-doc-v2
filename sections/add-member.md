## Add Account Member

### Description
This call adds a new member to the account. The call sends a new user invitation in case the user is not yet a member of Xplenty. 

The details returned for the member are:

* **id** - the member's numeric identifier
* **name** - the name given to the member upon creation
* **email** - the member's email
* **gravatar_email** - the member's gravatar email
* **avatar_url** - the url for the member's avatar
* **created_at** - the date and time the member was created
* **updated_at** - the date and time the member was last updated
* **role** - the member's role ("admin" or "member")
* **owner** - indicator if the member is the account owner

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
email|Y| |The user's email.
role|N|member|The role to assign to the member. Possible values are `member` or `admin`.

### Request (Curl Call) Syntax
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/members?email=<email>&role=<roleName>" -d ''
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
