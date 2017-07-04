## Get Facebook Ads Insights fields.

### Description
Informations about all fields supported for a given Facebook Ads Insights connection.

### Input Parameters
Required parameter is the **connection_id**.

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
api_version|N|v2.9|the Facebook API version to use for fetching the accounts (e.g. `v2.9`)


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/metadata/facebookadsinsights/:connection_id/fields" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{"api_version": "v2.9"}'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "category": "Metric",
    "data_type": "float",
    "default_alias": "video_p95_watched_actions_28d_click",
    "friendly_name": "Video Watches at 95%: 28d_click",
    "id": "video_p95_watched_actions_28d_click",
    "is_mandatory": "",
    "pig_data_type": "FLOAT",
    "request": {
      "action_attribution_windows": "28d_click",
      "fields": "video_p95_watched_actions"
    },
    "response": "$.video_p95_watched_actions[?(@.action_type=='video_view')].28d_click"
  },
  {
    "category": "Metric",
    "data_type": "float",
    "default_alias": "video_p95_watched_actions_28d_view",
    "friendly_name": "Video Watches at 95%: 28d_view",
    "id": "video_p95_watched_actions_28d_view",
    "is_mandatory": "",
    "pig_data_type": "FLOAT",
    "request": {
      "action_attribution_windows": "28d_view",
      "fields": "video_p95_watched_actions"
    },
    "response": "$.video_p95_watched_actions[?(@.action_type=='video_view')].28d_view"
  }
]
```
