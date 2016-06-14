## Update Payment Method and Plan

### Description
This call updates the payment method or [plan](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/plan.md) or both.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
billing_payment_token|N| |The valid payment token created through the billing provider (Stripe).
plan_id|N| |ID of the plan.

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/:account_id/api/payment_method" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "billing_payment_token": "valid-token",
    "plan_id": "starter"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "card_last_4": "1234",
  "card_number":"xxxx-xxxx-xxxx-1234",
  "expiration_date":"12/2015",
  "card_type":"Visa",
  "url":"https://api.xplenty.com/xplenation/api/payment_method"
}
```
