## Delete Package

### Description
This call deletes the given [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md).

Use this call when the package is no longer needed.

The details returned for removed package:

* **id** - the numeric package ID
* **name** - the name given to the package upon creation
* **description** - the description given to the package upon creation
* **variables** - the list of package variables
* **owner_id** - the numeric user id of the package owner
* **created_at** - the date and time the package was created
* **updated_at** - the date and time the package was last updated 
* **url** - the job resource URL


### Input Parameters
The **package ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/packages/<packageID>"
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
