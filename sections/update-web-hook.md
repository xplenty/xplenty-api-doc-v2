## Update Web Hook

### Description
Update an existing [web hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/web-hook.md), including adding and removing types of event notifications.

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
web_hook_id|Y| |The numeric web hook ID
events|N| |List of events. All existing events will be replaced with new.
add_events|N| |List of events to add. This parameter is consider only if **events** input is not passed
remove_events|N| |List of events to remove. This parameter is consider only if **events** input is not passed
active|N| |If hook is active.
basic_auth|N| |if basic authentication is required.
basic_auth_data|N| |Encoded (base64) data for basic auth (including user and password).
insecure_ssl|N| |If SSL certificate of the target server is verified.

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/:account_id/api/web_hooks/:web_hook_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "active": true,
    "url": "http://my.service.com",
    "basic_auth": true,
    "basic_auth_data": "YWRtaW46cGFzc3dvcmQ=",
    "insecure_ssl": true,
    "add_events": ["job.created", "cluster.terminated"],
    "remove_events": ["cluster.created"]
  }'
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
  "basic_auth": true
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
