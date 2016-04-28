## Post Connection validate.

### Description
Checks validation of connection.
List [connections](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connection.md) that are accessible by the authenticated user.

### Input Parameters
Required parameter is the **id** which is the connection id and **type** of the connection. Possible values of types are listed above.

For Database types:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
table|Y| |name of the table
schema_name|N| |

For Cloud Storage types:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
bucket|Y| |bucket or container
path|Y| |path
destination|N|false|


### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "/:account_id/api/connections/:type/:id/validate" \
  -H "Accept: application/vnd.xplenty+json; version=2"
  -d '{
    "table":"table",
    "schema_name":"schema"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "true"
}
