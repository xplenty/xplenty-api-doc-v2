## Create Delivery

### Description
Create a new [delivery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/delivery.md).

### Notes
* This call only triggers delivery creation, and therefore it returns the "disabled" status. To enable a delivery you need to change its status to "enabled" using [update delivery's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-delivery-information.md)
You can verify that a delivery has initialized successfully by [retrieving the delivery's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-delivery-information.md) and checking for the "enabled" status.
* You must save the delivery ID value returned in the response "id" field. You will use the value to refer to this delivery in subsequent API calls.

### Input Parameters
| Name                    | Required? | Default         | Description                                                          |
| ----                    | --------- | -------         | -----------                                                          |
| name                    | N         | Auto generated  | Name to assign to the new delivery                                   |
| description             | N         | blank           | Description to assign to the new delivery                            |
| interval_amount         | N         | 1               | Number of interval units between delivery's task executions          |
| interval_unit           | N         | days            | Delivery's interval unit. Possible values are: `minutes`, `hours`, `days`, `weeks`, `years`.|
| source                  | Y         |                 | Delivery's source properties                                         |
| destination             | Y         |                 | Delivery's destination properties                                    |

### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/deliveries" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Salesfore to Redshift",
    "description": "Delivery description",
    "interval": 1,
    "interval_amount": "days",
    "source": {
      "connection": {
        "type": "salesforce",
        "id": 1
      },
      "properties": {}
    },
    "destiantion": {
      "connection": {
        "type": "redshift",
        "id": 1
      },
      "properties": {
        "schema": "salesforce_prod"
      }
    }
  }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```

```json
{
  "id": 2,
  "name": "Salesfore to Redshift",
  "description": "Delivery description",
  "interval": 1,
  "interval_amount": "days",
  "source": {
    "connection": {
      "type": "salesforce",
      "id": 1
    },
    "properties": {}
  },
  "destiantion": {
    "connection": {
      "type": "redshift",
      "id": 1
    },
    "properties": {
      "schema": "salesforce_prod"
    }
  },
  "created_at": "2014-09-25T08:48:51Z",
  "updated_at": "2014-09-25T08:48:51Z",
  "url": "https://api.xplenty.com/xplenation/api/deliveries/2"
}
```