## Delete Web Hook

### Description
Delete an existing [web hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/web-hook.md).
You can deactivate ([update hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-web-hook.md) with **active** set to `false`) hook instead of removing it, if you need to disable it temporarly.

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
events|Y| |List of events.
active|N|true|If hook is active.
basic_auth|N|false|if basic authentication is required.
basic_auth_data|N| |Encoded (base64) data for basic auth (including user and password).
insecure_ssl|N|false|If SSL certificate of the target server is verified.

### Request (Curl Call) Example
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/web_hooks" \
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
  "type": "web_hook",
  "url": "http://my.service.com/notifications",
  "insecure_ssl": false,
  "basic_auth": true,
  "events": [
    {
      "id": 2,
      "name": "job.created",
      "last_response": {},
      "last_trigger_status": "none",
      "last_trigger_time": null
    },
    {
      "id": 3,
      "name": "cluster.terminated",
      "last_response": {},
      "last_trigger_status": "none",
      "last_trigger_time": null
    }
  ]
}
```
