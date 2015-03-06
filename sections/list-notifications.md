## List Authenticated User's Notifications

### Description
List [notifications](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/notification.md) of authenticated user.
Optionally, you can supply the input parameters to filter the list so that it contains unread or all notifications and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
all|N|false|Indicates if all notifications should be return all unread only.
sort|N|"created"|Possible values are  ```updated```, ```created```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The notifications will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The notifications list will only contain objects updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/notifications" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
        "sort":"updated",
        "direction":"asc",
        "since":"2013-01-17T22:41:21Z"
    }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id":2,
    "last_read_at":null,
    "title":"Cluster error",
    "message":"Something went wrong with cluster <a href=\"/test-account-2/clusters/2\">test-account-2/Test Cluster 2</a>. Our team is looking into it. We recommend you terminate it."
  },
  {
    "id":3,
    "last_read_at":null,
    "title":"Cluster available",
    "message":"Cluster <a href=\"/test-account-2/clusters/2\">test-account-2/Test Cluster 2</a> is available."
  }
]
```
