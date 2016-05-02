## Get BingAds accounts.

### Description
Informations about accounts and theirs campaings if **accounts** or **force_fetch** are set.

### Input Parameters
Required parameter is the **connection_id**.

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
accounts|N| |Accounts IDs to get campaings from
force_fetch|N|false|determines if get campaigns from all accounts or not


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "/:account_id/api/connections/metadata/bingads/:connection_id/accounts" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json


```
