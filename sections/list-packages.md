## List Packages

### Description
List [packages](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md) that are accessible by authenticated user.
You can use this information to monitor your packages.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
flow_type|N|"all"|Possible values are `workflow`, `dataflow`, `all`. The call will return only packages with the given flow_type, or all the packages if the "all" value is specified.


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/packages" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "flow_type": "workflow"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 2373,
    "name": "AWS CloudFront Log Analysis",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T07:09:18Z",
    "updated_at": "2014-04-13T19:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2373"
  },
  {
    "id": 2374,
    "name": "AWS CloudFront Log Analysis 2",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T08:09:18Z",
    "updated_at": "2014-04-13T20:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2374"
  }
]
```
