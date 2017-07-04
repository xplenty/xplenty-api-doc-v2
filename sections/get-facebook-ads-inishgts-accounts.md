## Get Facebook Ads Insights accounts.

### Description
Informations about all accounts accessible by a given Facebook Ads Insights connection.

### Input Parameters
Required parameter is the **connection_id**.

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
api_version|N|v2.9|the Facebook API version to use for fetching the accounts (e.g. `v2.9`)


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/metadata/facebookadsinsights/:connection_id/accounts" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{"api_version": "v2.9"}'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
      "account_id": "111111111111111",
      "id": "act_111111111111111",
      "name": "First Account Name"
  },
  {
      "account_id": "222222222222222",
      "id": "act_222222222222222",
      "name": "Second Account Name"
  },
  {
      "account_id": "333333333333333",
      "id": "act_333333333333333",
      "name": "Third Account Name"
  }
]
```
