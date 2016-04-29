## Get Salesforce objects

### Description
Information about salesforce objects.

### Input Parameters
Required parameter is the **connection_id**.
Possible to add **force_fetch** which determines if clear cache or not.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "/:account_id/api/connections/metadata/salesforce/:connection_id/objects" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json

```
