## Delete Package

### Description
This call deletes the given [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md).

Use this call when the package is no longer needed.

### Input Parameters
The **package ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/packages/:package_id" \
  -H "Accept: application/vnd.xplenty+json, version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":3,
  "name":"Test Job 3",
  "description":null,
  "variables":{},
  "flow_type":"dataflow",
  "owner_id":5,
  "created_at":"2015-02-26T11:46:05Z",
  "updated_at":"2015-02-26T11:46:05Z",
  "url":"http://xplenty.com/test-account-3/api/packages/3"
}
```
