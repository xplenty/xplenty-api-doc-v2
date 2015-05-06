## List Authenticated User's Notifications

### Description
This call returns a list of [notifications](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/notification.md) of the authenticated user.
Optionally, you can supply the input parameters to filter the list so that it contains only unread notifications or all notifications, and to determine the order by which the list will be sorted.

The details returned for each notification are:

* **id** - the notification's numeric identifier
* **title** - the notification's title
* **message** - the notification's message
* **last_read_at** - the time the notification was last checked
* **created_at** - the date and time the notification was created
* **updated_at** - the date and time the notification was last updated

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
all|N|false|The call will return only unread notifications if the value is set to 'false'.
sort|N|"created"|Possible values are  ```updated```, ```created```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The notifications will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The notifications list will only contain objects updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/user/notifications" \
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
    "message":"Something went wrong with cluster <a href=\"https://api.xplenty.com/test-account-2/clusters/2\">test-account-2/Test Cluster 2</a>. Our team is looking into it. We recommend you terminate it.",
    "created_at":"2013-01-17T22:41:21Z",
    "updated_at":"2013-01-17T22:41:21Z"
  },
  {
    "id":3,
    "last_read_at":null,
    "title":"Cluster available",
    "message":"Cluster <a href=\"https://api.xplenty.com/test-account-2/clusters/2\">test-account-2/Test Cluster 2</a> is available.",
    "created_at":"2013-01-18T22:41:21Z",
    "updated_at":"2013-01-18T22:41:21Z"
  }
]
```
