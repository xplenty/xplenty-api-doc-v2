## Post Connection validate.

### Description
Checks validation of connection.
List [connections](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connection.md) that are accessible by the authenticated user.

### Input Parameters
Required parameter is the **id** which is the connection id and **type** of the connection. Values of types are listed above.
Possible **type** is also ```curl```, in that case, **id** is not required.

For Database types:
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
where_clause|N| |where clause, syntax can be found at https://developer.salesforce.com/docs/atlas.en-us.soql_sosl.meta/soql_sosl/sforce_api_calls_soql_select_conditionexpression.htm
table|Y| | name of the table
row_count|N|20|row limit
schema_name|N| |

For Cloud Storage types:
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
bucket|Y| |bucket or container
path|Y| |path
file_type|N|file|possible ```file``` or ```service```
lines|N|20|lines limit
delimiter|N|\t|
skip_header|N|false|in case of fields name in headers
record_delimiter|N|New line|
record_type|N|Delimited values|
quote|N|none|quotation marks
escape|N| |escape marks

For curl type:
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
bucket|Y| |bucket or container
path|Y| |path
destination|N|false|




### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "/:account_id/api/connections/:type/:id/validate" \
  -H "Accept: application/vnd.xplenty+json; version=2"
  -d '{
    "table":"tableName"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "data": [],
  "raw": [
    "{ \"_id\" : { \"$oid\" : \"5721f8e5d6bfd23191717153\"} , \"item\" : \"card\" , \"qty\" : 15.0}"
  ],
  "fields": [
    {
      "item": "string"
    },
    {
      "qty": "double"
    },
    {
      "_id": "string"
    }
  ]
}
```
