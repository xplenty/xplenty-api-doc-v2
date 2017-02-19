## Update Web Hook

### Description
Update an existing hook, including adding and removing types of event notifications.

Xplenty provides the following types of hooks:

* [Web Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/web-hook.md)
* [Slack Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/slack-hook.md)
* [Hip Chat Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/hip-chat-hook.md)
* [Email Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/email-hook.md)
* [Pager Duty Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/pager-duty-hook.md)

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
hook_id|Y| |The numeric hook ID
name|N| |Name of the hook. Please check detailed hook description for default value.
events|N| |List of events. All existing events will be replaced with new.
active|N| |If hook is active.
settings|Y| |Settings specific for the type of hook.

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/:account_id/api/hooks/:hook_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "active": true,
    "settings": {
      "url": "http://my.service.com/notifications",
      "insecure_ssl": false,
      "basic_auth": true
    },
    "events": ["job.submitted", "cluster.terminated"]
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
  "type": "web",
  "settings": {
    "url": "http://my.service.com/notifications",
    "insecure_ssl": false,
    "basic_auth": true
  },
  "events": ["job.submitted", "cluster.terminated"]
}
```
