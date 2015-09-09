## List Web Hooks

### Description
List all [web hooks](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/web-hook.md) for specific account. Optionally, you can determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
sort|N|"created"|Possible values are  ```updated```, ```created```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The web hooks will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The account list will only contain web hooks updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET-u api_key: "https://api.xplenty.com/:account_id/api/hooks/web" \
  -H "Accept: application/vnd.xplenty+json, version=2"
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
    "events": [
      {
        "id": 1,
        "name": "job.stopped",
        "last_response": {},
        "last_trigger_status": "none",
        "last_trigger_time": null
      },
      {
        "id": 2,
        "name": "cluster",
        "last_response": {},
        "last_trigger_status": "none",
        "last_trigger_time": null
      }
    ]
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
    "events": [
      {
        "id": 3,
        "name": "job.created",
        "last_response": {},
        "last_trigger_status": "none",
        "last_trigger_time": null
      },
      {
        "id": 4,
        "name": "cluster.terminated",
        "last_response": {
          "code": "200",
          "body": "OK"
        },
        "last_trigger_status": "none",
        "last_trigger_time": null
      }
    ]
  }
]
```
