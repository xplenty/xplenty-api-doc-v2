## List available Regions

### Description
This call returns information for the list of regions supported by Xplenty. You can also select regions for particular Brand.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
type|N| |The resource type to return the supported regions for. Supported values are `redshift`, `bigquery`, `s3`, `snowflake`, `athena`.

### Request (Curl Call) Syntax
```shell
$curl -X GET -u api_key: "https://api.xplenty.com/regions/:type" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::us-east-1",
    "name": "AWS - US East (N. Virginia)",
    "short_name": "US East (Northern Virginia)"
  },
  {
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::us-west-1",
    "name": "AWS - US West (N. California)",
    "short_name": "US West (Northern California)"
  },
  {
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::us-west-2",
    "name": "AWS - US West (Oregon)",
    "short_name": "US West (Oregon)"
  },
  {
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::eu-west-1",
    "name": "AWS - EU (Ireland)",
    "short_name": "EU (Ireland)"
  },
  {
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::ap-southeast-1",
    "name": "AWS - Asia Pacific (Singapore)",
    "short_name": "Asia Pacific (Singapore)"
  },
  {
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::ap-southeast-2",
    "name": "AWS - Asia Pacific (Sydney)",
    "short_name": "Asia Pacific (Sydney)"
  },
  {
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::ap-northeast-1",
    "name": "AWS - Asia Pacific (Tokyo)",
    "short_name": "Asia Pacific (Tokyo)"
  },
  {
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::sa-east-1",
    "name": "AWS - South America (S\u00e3o Paulo)",
    "short_name": "South America (S\u00e3o Paulo)"
  },
  {
    "group_name": "Google Cloud",
    "id": "gcloud::asia-east1",
    "name": "Google Cloud - East Asia",
    "short_name": "East Asia"
  },
  {
    "group_name": "Google Cloud",
    "id": "gcloud::europe-west1",
    "name": "Google Cloud - Western Europe",
    "short_name": "Western Europe"
  },
  {
    "group_name": "Google Cloud",
    "id": "gcloud::us-central1",
    "name": "Google Cloud - Central US",
    "short_name": "Central US"
  }
]
```