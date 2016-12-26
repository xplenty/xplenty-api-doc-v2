## List available Account Regions

### Description
This call returns information for the list of regions that are available for your account.
You can use this information to verify the regions in which you can create a cluster.

### Request (Curl Call) Syntax
```shell
$curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/regions" \
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
    "group_name": "SoftLayer CloudLayer",
    "id": "soft-layer::dal05",
    "name": "SoftLayer - Dallas 5 (DAL05)",
    "short_name": "Dallas 5 (DAL05)"
  },
  {
    "group_name": "SoftLayer CloudLayer",
    "id": "soft-layer::ams01",
    "name": "SoftLayer - Amsterdam 1 (AMS01)",
    "short_name": "Amsterdam 1 (AMS01)"
  },
  {
    "group_name": "SoftLayer CloudLayer",
    "id": "soft-layer::sng01",
    "name": "SoftLayer - Singapore 1 (SNG01)",
    "short_name": "Singapore 1 (SNG01)"
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
