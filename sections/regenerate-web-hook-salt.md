## Regenerate Web Hook Salt

### Description
Re-generate salt of the [web hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/web-hook.md).

### Input Parameters
The **web hook ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/:account_id/api/web_hooks/:web_hook_id/regenerate_salt" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" -d ''
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
