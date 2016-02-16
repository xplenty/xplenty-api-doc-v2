## List Hooks

### Description
List all hooks for specific account. Optionally, you can determine the order by which the list will be sorted.

Xplenty provides tha following types of hooks:

* [Web Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/web-hook.md)
* [Slack Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/slack-hook.md)
* [Hip Chat Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/hip-chat-hook.md)
* [Email Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/email-hook.md)
* [Pager Duty Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/pager-duty-hook.md)

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
sort|N|"created"|Possible values are  ```name```, ```updated```, ```created```.
type|N|"all" |Type of the hook (every article about particular hook contains information about type) or ```all```. The call will return only hooks with the given types, or all the hooks if the "all" value is specified. Values can be joined with commas, e.g. 'web,email,slack'.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The hooks will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The account list will only contain hooks updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET-u api_key: "https://api.xplenty.com/:account_id/api/hooks" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" -d '{
    "type": "web"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
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
  },
  {
    "id": 2,
    "salt": "56f07c3f04d37c097d6a2c22dcefa6f0fc1610cba08beb7c293988f42cb8ed14",
    "active": true,
    "type": "web",
    "settings": {
      "url": "http://my.service.com/notifications",
      "insecure_ssl": false,
      "basic_auth": true
    },
    "events": ["job.submitted", "cluster.terminated"]
  }
]
```
