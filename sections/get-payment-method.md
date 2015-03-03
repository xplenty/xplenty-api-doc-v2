## Get Payment Method

### Description
This call returns the details of the payment method on file, for the given account. If there is no payment method defined, returns Resource not found (404) message.

The details returned for the method are:

* **card_last_4** - card's number last 4 digits
* **card_number** - obfuscated card number with last 4 digits being visible
* **expiration_date** - card's expiration date
* **card_type** - card's type

### Input Parameters

The **account ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/payment_method" \
  -H "Accept: application/vnd.xplenty+json, version=2" 
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
  "card_type":"Visa"
}
```
