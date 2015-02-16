## Delete Account Connection

### Description
This call deletes the given connection.

Use this call when the connection is no longer needed.

### Input Parameters
The **connection type** and **connection resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/connections/<connectionType>/<connectionID>"
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
  "type":"s3"
}
```
