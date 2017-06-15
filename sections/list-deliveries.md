## List Deliveries

### Description
List [deliveries](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/delivery.md) that are accessible by authenticated user.
You can use this information to monitor your deliveries and their status.
Optionally, you can supply the input parameters to filter the delivery list so that it contains only deliveries with a specific status, and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
status|N|"all"|Possible values are any status listed above or ```all```. The call will return only deliveries with the given status, or all the deliveries if the "all" value is specified.
sort|N|"created"|Possible values are ```updated``` or ```created```. The delivery list will be sorted by the deliveries' "updated_at" or "created_at" value respectively.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The deliveries will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The delivery list will only contain deliveries updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/deliveries" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json"
```
### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 2,
    "name": "Salesfore to Redshift",
    "description": null,
    "interval_unit": "days",
    "interval_amount": 1,
    "source": {
      "connection": {
        "type": "salesforce",
        "id": 1
      },
      "properties": {}
    },
    "destination": {
      "connection": {
        "type": "redshift",
        "id": 1
      },
      "properties": {
        "schema": "salesforce_prod"
      }
    },
    "status": "idle",
    "owner_id": 27,
    "created_at": "2014-09-25T08:48:51Z",
    "updated_at": "2014-09-25T08:48:51Z",
    "url": "https://api.xplenty.com/xplenation/api/deliveries/2"
  }
]
```
