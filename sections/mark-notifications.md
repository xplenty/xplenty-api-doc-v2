## Mark Notifications as read

### Description
Marks the authenticated user's [notifications](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/notification.md) as read.
This call returns empty response.

### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/user/notifications/mark" \
  -H "Accept: application/vnd.xplenty+json, version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 Created
```