## List Connection Types

### Description
List all connection types that are available with related groups.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/types" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "type":"adwords",
    "name":"Google AdWords",
    "description":"Google (PPC) Pay-Per-Click online advertising service",
    "icon_url":"https://xplenty.com/assets/vendor/google-adwords.png",
    "groups":
    [
      {
        "group_type":"services",
        "group_name":"Services"
      }
    ]
  },
  {
    "type":"analytics",
    "name":"Google Analytics",
    "description":"Google web analytics & reporting service",
    "icon_url":"https://xplenty.com/assets/vendor/google-analytics.png",
    "groups":
    [
      {
        "group_type":"services",
        "group_name":"Services"
      }
    ]
  },
  {
    "type":"bigquery",
    "name":"Google BigQuery",
    "description":"Real time Big Data analytics in the cloud provided by Google",
    "icon_url":"http://xplenty.com/assets/vendor/google-big-query.png",
    "groups":
    [
      {
        "group_type":"analytical",
        "group_name":"Analytical Databases"
      }
    ]
  }
]
```
