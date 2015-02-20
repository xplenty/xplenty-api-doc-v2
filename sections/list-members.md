## List Account Members

### Description
This call returns information for a list of account members. Optionally, you can supply the input parameters to filter the member list so that it contains
only members with a specific role or email, and to determine the order by which the list will be sorted.

The details returned for each member are:

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
role|N|"all" |Possible values are ```admin```, ```member```, ```all```. The call will return only members with the given role, or all the members if value is not specified or the 'all' value is specified.
email|N| |The call will return only the member with the given email, or all the members if a value is not specified.
sort|N|"created"|Possible values are  ```updated```, ```created```, ```name```, ```email```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The members will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The member list will only contain users updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/members?role=<typeFilter>&email=<emailField>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
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
  },
  {
    "id":2,
    "name":"John Smith",
    "email":"john@smith.com",
    "gravatar_email":"john@smith.com",
    "avatar_url":"https://xplenty.com/path/to/avatar.png",
    "created_at": "2013-01-17T22:41:21Z",
    "updated_at": "2013-01-17T22:41:21Z",
    "role":"member",
    "owner":false
  }
]
```
