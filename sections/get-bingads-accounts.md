## Get BingAds accounts.

### Description
Informations about all accounts and campaings for specified **accounts** or if **force_fetch** is set.

### Input Parameters
Required parameter is the **connection_id**.

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
api_version|N|v9|the BingAds API version to use for fetching the accounts (e.g. `v9`, `v10`)
accounts|N| |Accounts IDs to get campaings from
force_fetch|N|false|determines if caching should be bypassed


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/metadata/bingads/:connection_id/accounts" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "accounts": ["123"],
    "api_version": "v10"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "account_id": "123",
    "account_name": "Account_1",
    "campaigns": [
      {
        "campaign_id": "432",
        "campaign_status": "Paused",
        "campaign_name": "Campaign_Name_1"
      },
      {
        "campaign_id": "543",
        "campaign_status": "Paused",
        "campaign_name": "Campaign_Name_2"
      },
      {
        "campaign_id": "643",
        "campaign_status": "Paused",
        "campaign_name": "Campaign_Name_3"
      }
    ]
  },
  {
    "account_id": "456",
    "account_name": "Account_2",
    "campaigns": []
  },
  {
    "account_id": "678",
    "account_name": "Account_3",
    "campaigns": []
  }
]
```
