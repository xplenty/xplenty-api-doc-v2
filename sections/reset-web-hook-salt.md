## Reset Web Hook Salt

### Description
Reset salt of the [web hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/web-hook.md).

### Input Parameters
The **web hook ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/:account_id/api/hooks/:web_hook_id/reset_salt" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" -d '{
    "type":"web"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "salt": "2db5b8725e2d86aba40d43f6e403bdf483b8535a3d0011d34b3687140b52bc8c"
}
```
