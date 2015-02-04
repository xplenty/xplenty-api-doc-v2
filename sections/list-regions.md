## List available Regions

### Description
This call returns information for the list of regions that are available for account.
You can use this information to verify in which regions you can create a cluster.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/regions"
```
### Response Example
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
