## Export Package as JSON

### Description
Export all the components within the package as a JSON file

### Input Parameters
The **package ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
On this request, the response will be stored to the `package.json` file which contains package's dataflow 
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/packages/:package_id/export" \
  -H "Accept: application/vnd.xplenty+json; version=2 > package.json" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```
