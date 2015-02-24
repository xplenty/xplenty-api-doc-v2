## Delete Account Member

### Description
This call deletes the member from the account. It does not remove the user, just the account membership.

The details returned for the deleted member are:

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
The **user ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/members/<userID>"
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
  "avatar_url":"https://xplenty.com/path/to/avatar.png",
  "created_at": "2013-01-17T22:41:21Z",
  "updated_at": "2013-01-17T22:41:21Z",
  "role":"admin",
  "owner":true
}
```
