## Reset Hook Salt

### Description
Reset salt of the hook.

Xplenty provides tha following types of hooks:

* [Web Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/web-hook.md)
* [Slack Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/slack-hook.md)
* [Hip Chat Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/hip-chat-hook.md)
* [Email Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/email-hook.md)
* [Pager Duty Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/pager-duty-hook.md)

### Input Parameters
The **hook ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/:account_id/api/hooks/:web_hook_id/reset_salt" \
  -H "Accept: application/vnd.xplenty+json; version=2" -H "Content-Type: application/json"
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
