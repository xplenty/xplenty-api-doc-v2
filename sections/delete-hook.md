## Delete Hook

### Description
Delete an existing hook. You can deactivate hook ([update hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-hook.md) with **active** field set to `false`) instead of removing it, if you need to disable it temporarly.

Xplenty provides tha following types of hooks:

* [Web Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/web-hook.md)
* [Slack Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/slack-hook.md)
* [Hip Chat Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/hip-chat-hook.md)
* [Email Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/email-hook.md)
* [Pager Duty Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/pager-duty-hook.md)


### Input Parameters
The **hook ID** must be supplied at the end of the request URL.

### Request (Curl Call) Example
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/hooks/:hook_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" -H "Content-Type: application/json"
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
  "events": ["job.submitted", "cluster.terminated"],
  "hook_notifications_count":0,
  "none_hook_notifications_count":0,
  "request_timeout_hook_notifications_count":0,
  "success_hook_notifications_count":0,
  "error_hook_notifications_count":0
}
```
