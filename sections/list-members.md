## List Account Members

### Description
List existing account [members](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/user.md).
Optionally, you can supply the input parameters to filter the member list so that it contains user with specific role or email only and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
role|N| |Possible values: admin, member, all. The call will return only members with the given role, or all the members if value is not specified or 'all' param was used.
email|N| |The call will return one member with the given email, or all the members if value is not specified.
sort|N|"created"|Possible values are  ```updated```, ```created```, ```name```, ```email```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The members will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The member list will only contain users updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/members" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
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
    "owner":true,
    "url": "https://api.xplenty.com/xplenation/api/members/1",
    "html_url": "https://xplenty.com/xplenation/members/1"
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
    "owner":false,
    "url": "https://api.xplenty.com/xplenation/api/members/2",
    "html_url": "https://xplenty.com/xplenation/members/2"
  }
]
```
