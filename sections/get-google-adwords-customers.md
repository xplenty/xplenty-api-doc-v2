## Get Google AdWords customers.

### Description
Informations about all customers accessible by a given Google AdWords connection.

### Input Parameters
Required parameter is the **connection_id**.

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
force_fetch|N|false|determines if caching should be bypassed


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/metadata/adwords/:connection_id/customers" \
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
    "can_manage_clients": false,
    "name": "Customer 1",
    "customer_id": "123456789"
  }
]
```
