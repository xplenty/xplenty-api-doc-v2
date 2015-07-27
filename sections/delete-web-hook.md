## Delete Web Hook

### Description
Delete an existing [web hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/web-hook.md).
You can deactivate hook ([update hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-web-hook.md) with **active** field set to `false`) instead of removing it, if you need to disable it temporarly.

### Input Parameters
The **web hook ID** must be supplied at the end of the request URL.

### Request (Curl Call) Example
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/hooks/web/:web_hook_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 1,
  "salt": "2db5b8725e2d86aba40d43f6e403bdf483b8535a3d0011d34b3687140b52bc8c",
  "active": true,
  "type": "web",
  "url": "http://my.service.com/notifications",
  "insecure_ssl": false,
  "basic_auth": true
}
```
