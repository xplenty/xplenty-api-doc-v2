## List Package Validations

### Description
List [validations](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package-validation.md) for specific package.
Optionally, you can supply the input parameters to filter the validation list so that it contains only validations with a specific status, and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
package_id|Y| |The **package ID** must be supplied at the end of the request URL.
status|N|"all"|Possible values are `running`, `completed`, `failed` or `all`. The call will return only validations with the given status, or all the validations if the "all" value is specified.
sort|N|"created"|Possible values are `updated` or `created`. The validation list will be sorted by the validations' "updated_at" or "created_at" value respectively.
direction|N|"desc"|Possible values are: `asc`, `desc`. The validations will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The validation list will only contain validations updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: `YYYY-MM-DDTHH:MM:SSZ`. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/accounts/:account_id/packages/:package_id/validations" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
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
  },
    {
    "id": 2,
    "status": "running",
    "status_message": null,
    "account_id": 5,
    "owner_id": 8,
    "runtime": null,
    "errors": [],
    "created_at": "2015-04-22T07:49:02Z",
    "updated_at": "2015-04-22T07:49:02Z",
    "package_id": 5,
    "url": "https://api.xplenty.com/xplenation/api/packages/5/validations/2"
  }
]
```
