## Get Package Validation Information

### Description
Returns information about progress of the [package validation](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package-validation.md) process.

### Input Parameters
The **package ID** and **validation ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/packages/:package_id/validations/:validation_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 1,
  "status": "running",
  "status_message": null,
  "account_id": 5,
  "owner_id": 8,
  "runtime": null,
  "errors": [],
  "created_at": "2015-04-22T07:49:02Z",
  "updated_at": "2015-04-22T07:49:02Z",
  "package_id": 5,
  "url": "https://api.xplenty.com/xplenation/api/packages/5/validations/1"
}
```
