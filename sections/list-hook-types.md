## List Hook Types

### Description
List all hook types that are available with related groups.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/hooks/types" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "type":"email",
    "name":"Email",
    "description":"Our Email integration enables you to receive real-time email alerts about your account activity.",
    "icon_url":"https://xplenty.com/assets/vendor/hooks/emailhook.png",
    "groups": [
      {
        "group_type":"email",
        "group_name":"Email"
      }
    ]
  },
  {
    "type":"hipchat",
    "name":"HipChat",
    "description":"Our HipChat integration enables you to receive real-time updates about your account activity into your HipChat rooms.",
    "icon_url":"https://xplenty.com/assets/vendor/hooks/hipchathook.png",
    "groups": [
      {
        "group_type":"chat",
        "group_name":"Chat"
      }
    ]
  }
]
```
