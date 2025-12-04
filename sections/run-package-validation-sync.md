## Run Package Validation (Synchronous)

### Description
Runs a new [validation](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package-validation.md) process for the package synchronously and returns the completed validation result in a single request.

Unlike the asynchronous [Run Package Validation](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/run-package-validation.md) endpoint, this endpoint waits for the validation to complete before returning the response. This is useful when you need immediate validation results without polling.

### Notes
* This endpoint blocks until the validation completes (either successfully or with failure).
* The response contains the final validation status (`completed` or `failed`) along with any errors.
* For long-running validations, consider using the asynchronous validation endpoint instead.

### Input Parameters
The **package ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/packages/:package_id/validate" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json"
```

### Response Example (Successful Validation)
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 1,
  "status": "completed",
  "status_message": "Validation successful",
  "account_id": 5,
  "owner_id": 8,
  "runtime": 150,
  "errors": [],
  "created_at": "2015-04-22T07:49:02Z",
  "updated_at": "2015-04-22T07:49:05Z",
  "package_id": 5,
  "url": "https://api.xplenty.com/xplenation/api/packages/5/validations/1"
}
```

### Response Example (Failed Validation)
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 2,
  "status": "failed",
  "status_message": "Syntax error in script",
  "account_id": 5,
  "owner_id": 8,
  "runtime": 50,
  "errors": [
    {
      "message": "Invalid expression at line 5"
    }
  ],
  "created_at": "2015-04-22T07:49:02Z",
  "updated_at": "2015-04-22T07:49:03Z",
  "package_id": 5,
  "url": "https://api.xplenty.com/xplenation/api/packages/5/validations/2"
}
```
