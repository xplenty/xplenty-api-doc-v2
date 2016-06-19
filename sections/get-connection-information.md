## Get Account Connection Information

### Description
Information about existing account [connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connection.md).

### Input Parameters
The **connection type** and **connection ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/:type/:id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 323,
  "name": "App Logs (MongoDB)",
  "type": "mongo",
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z",
  "url": "https://api.xplenty.com/xplenation/api/connections/mongo/323"
}
```
