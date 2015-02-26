## Update Package

### Description
This call updates details of the given [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md).

The details returned for the updated package are:

* **id** - the numeric package ID
* **name** - the name given to the package
* **description** - the description given to the package
* **variables** - the list of package variables in the hash format, e.g. { "variable1" : "321" }
* **owner_id** - the numeric user id of the package owner
* **created_at** - the date and time the package was created
* **updated_at** - the date and time the package was last updated 
* **url** - the job resource URL


### Input Parameters
Name|Required?|Default|Description|
|----|---------|-------|-----------|
account_id|Y| |The account ID must be supplied in the request URL.
id|Y| |The package ID must be supplied at the end of the request URL.
name|N| |Name of the package
description|N| |Description of the package
data_flow_json|N| |Data flow prepared in JSON format
variables|N| |The list of package variables in the hash format

### Request (Curl Call) Syntax
```shell
curl -X PUT  -H "Content-Type: application/json" -H "Accept: application/vnd.xplenty+json, version=2" 
     -u <APIkey>: "https://api.xplenty.com/<accountID>/packages/<packageID>"
     -d '{
        "name" : "Test package 1",
        "description" : "Sample description",
        "data_flow_json" : { "step1" : "value" },
        "variables" : { "variable1" : "123", "variable2" : "456" }
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
  "url":"http://xplenty.com/test-account-3/api/packages/3"
}
```
