## List supported Time Zones

### Description
This call returns list of supported Time Zones.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/timezones" \
  -H "Accept: application/vnd.xplenty+json, version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "name": "(GMT-10:00) Hawaii",
    "id": "Hawaii"
  },
  {
    "name": "(GMT-09:00) Alaska",
    "id": "Alaska"
  },
  {
    "name": "(GMT-08:00) Pacific Time (US & Canada)",
    "id": "Pacific Time (US & Canada)"
  },
  {
    "name": "(GMT-07:00) Arizona",
    "id": "Arizona"
  },
  {
    "name": "(GMT-07:00) Mountain Time (US & Canada)",
    "id": "Mountain Time (US & Canada)"
  },
  {
    "name": "(GMT-06:00) Central Time (US & Canada)",
    "id": "Central Time (US & Canada)"
  },
  {
    "name": "(GMT-05:00) Eastern Time (US & Canada)",
    "id": "Eastern Time (US & Canada)"
  },
  {
    "name": "(GMT-05:00) Indiana (East)",
    "id": "Indiana (East)"
  }
]
```
