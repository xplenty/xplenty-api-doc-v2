## Delete Account Connection

### Description
Delete an existing [connection](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connection.md).

### Notes
Please note that deleting the connection will **invalidate all items referencing it**.

### Input Parameters
The **connection type** and **connection ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/connections/:type/:connection_id" \
  -H "Accept: application/vnd.xplenty+json, version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":234,
  "name":"Amazon S3 sample connection",
  "created_at":"2015-02-16T07:58:52Z",
  "updated_at":"2015-02-16T07:58:52Z",
  "type":"s3",
  "url":"https://api.xplenty.com/:account_id/api/connections/:type/:connection_id
}
```
