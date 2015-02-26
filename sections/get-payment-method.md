## Get Payment Method

### Description
This call returns the details of the payment method for the given account. If there is no payment method defined, returns Resource not found (404) message.

The details returned for the method are:

* **card_last_4** - last 4 digits of card number
* **card_number** - card number with last 4th digits visible
* **expiration_date** - card's expiration date
* **card_type** - card's type


### Input Parameters

The **account ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/payment_method"
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
