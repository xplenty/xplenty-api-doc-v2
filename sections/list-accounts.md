## List Account Members

### Description
This call returns list of active accounts where authenticated user is a member (can have admin or just member role).

Optionally, you can supply the input parameters to filter the account list so that it contains
account with specific role or id only and to determine the order by which the list will be sorted.


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
role|N| |Possible values: admin, member, all. The call will return only accounts where authenticated user has given role, or all the accounts if value is not specified or 'all' value was used.
id|N| |The call will return one account with the given id, or all of the them if value is not specified.
sort|N|"created"|Possible values are  ```updated```, ```created```, ```id```, ```name```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The accounts will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The account list will only contain accounts updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/accounts?role=<roleFilter>&id=<idField>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id":"xplenty-admin",
    "name":"Xplenty Admin",
    "region":"amazon-web-services::us-east-1",
    "location":null,
    "billing_email":"admin@xplenty.com",
    "gravatar_email":""admin@xplenty.com"",
    "avatar_url":"http://gravatar.com/avatar/d41d8cd98f00b204e9800998ecf8427e.png?d=retro&s=140",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z",
    "schedules_count":0,
    "connections_count":2,
    "role":"admin",
    "owner":true
  },
  {
    "id":"sample-admin",
    "name":"Sample Admin",
    "region":"amazon-web-services::us-east-1",
    "location":null,
    "billing_email":"admin@example.com",
    "gravatar_email":""admin@example.com"",
    "avatar_url":"http://gravatar.com/avatar/d24d8cd923f00b204e9800998ecf8427e.png?d=retro&s=140",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z",
    "schedules_count":0,
    "connections_count":2,
    "role":"admin",
    "owner":true
  }
]
```
