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
    "name": "AWS - Us East (N. Virginia)",
    "group_name": "Amazon Web Services",
    "id": "amazon-web-services::us-east-1"
  },
  {
    "name": "Rackspace - Dallas (DFW)",
    "group_name": "Rackspace Cloud Servers",
    "id": "rackspace::dfw"
  },
  {
    "name": "Google Cloud",
    "group_name": "Google Cloud - US (Central)",
    "id": "us-central1"
  }
]
```
