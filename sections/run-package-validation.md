## Run Package Validation

### Description
Runs new [validation](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package-validation.md) process for the package and returns information about status and tracking url.

### Notes
* You must save the validation ID value returned in the response "id" field. You will use the value to refer to this validation in subsequent API calls. You can also use the generated tracking URL which contains the validation ID.

### Input Parameters
The **package ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/packages/:package_id/validations" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json"
```

### Response Example
```HTTP
HTTP/1.1 201 Created
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
