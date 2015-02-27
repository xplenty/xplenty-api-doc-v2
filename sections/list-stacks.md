## List supported Stacks

### Description
This call returns information for the list of supported Stacks.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/stacks" \
  -H "Accept: application/vnd.xplenty+json, version=2" 
```
### Response Example
```json
[
  {
    "name": "Mint Everest",
    "id": "mint-everest"
  },
  {
    "name": "Lime Everest",
    "id": "lime-everest"
  },
  {
    "name": "Blue Everest",
    "id": "blue-everest"
  }
]
```
