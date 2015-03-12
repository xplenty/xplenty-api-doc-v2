## Update Package

### Description
Update an existing [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md).

### Input Parameters
Name|Required?|Default|Description|
|----|---------|-------|-----------|
account_id|Y| |The account ID must be supplied in the request URL.
id|Y| |The package ID must be supplied at the end of the request URL.
name|N| |Name of the package
description|N| |Description of the package
data_flow_json|N| |Data flow prepared in JSON format
variables|N| |The list of package variables in its JSON format

### Request (Curl Call) Syntax
```shell
$ curl -X PUT  -u api_key: "https://api.xplenty.com/:account_id/api/packages/:package_id" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Test package 1",
    "description": "Sample description",
    "variables": { 
      "variable1": "123", 
      "variable2": "456" 
    }
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":3,
  "name":"Test Package 1",
  "description":null,
  "variables":{},
  "flow_type":"dataflow",
  "owner_id":5,
  "created_at":"2015-02-26T11:46:05Z",
  "updated_at":"2015-02-26T11:46:05Z",
  "url":"https://api.xplenty.com/xplenation/api/packages/3"
}
```
