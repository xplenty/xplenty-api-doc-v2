## Delete Delivery

### Description
Delete an existing [delivery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/delivery.md).

### Notes
* This call removes the delivery all together - contrary to some other resources this one **won't** be archived / updated.
You can verify that a delivery has been removed successfully by [retrieving the delivery's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-delivery-information.md).

### Input Parameters
The **delivery resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/deliveries/:delivery_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 2,
  "name": "Salesfore to Redshift",
  "description": null,
  "interval_unit": 1,
  "interval_amount": "days",
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
  "status": "enabled",
  "owner_id": 27,
  "created_at": "2014-09-25T08:48:51Z",
  "updated_at": "2014-09-25T08:48:51Z",
  "url": "https://api.xplenty.com/xplenation/api/deliveries/2"
}
```
