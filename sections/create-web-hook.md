## Create Web Hook

### Description
Create a new [web hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/web-hook.md).

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
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/hooks/web" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "active": true,
    "url": "http://my.service.com",
    "basic_auth": true,
    "basic_auth_data": "YWRtaW46cGFzc3dvcmQ=",
    "insecure_ssl": true,
    "events": ["job.created", "cluster.terminated"]
  }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```

```json
{
  "id": 1,
  "salt": "2db5b8725e2d86aba40d43f6e403bdf483b8535a3d0011d34b3687140b52bc8c",
  "active": true,
  "type": "web",
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
