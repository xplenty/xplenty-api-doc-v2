## Create Package

### Description
Create a new [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md).

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
source_package_id|N| |If it is provided, the new package will be a copy of package with this ID
package_template_id|N| |If it is provided, the new package will be created based on the template that is associated with this ID
name|N|"Untitled package"|Name of the package
description|N| |Description of the package
data_flow_json|N| |Data flow prepared in JSON format
variables|N| |The list of package variables in its JSON format
flow_type|N|"dataflow"|Flow type of the package. Possible values: `dataflow`, `workflow`

### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/packages" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
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
HTTP/1.1 201 Created
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
  "url":"https://api.xplenty.com/xplenation/api/packages/3",
  "status":"active"
}
```
