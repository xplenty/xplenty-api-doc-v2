## List supported Stacks

### Description
This call returns information for the list of supported Stacks.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/stacks"
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
