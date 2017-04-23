## List Invoices

### Description
List [invoices](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/invoice.md) that are accessible by authenticated user.
You can use this information to monitor your invoices.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
sort|N|"created"|Possible values are `updated`, `created`, `issued` or `number`. The invoices list will be sorted by the invoices' `updated_at`, `created_at`, `issued` or `number` value respectively.
direction|N|"desc"|Possible values are: `asc`, `desc`. The invoices will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The invoices list will only contain invoices updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/invoices" \
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
    "created_at": "2017-04-19T10:36:10Z",
    "id": 4198,
    "issued_at": "2017-04-19T10:35:46Z",
    "notes": null,
    "number": 312382,
    "status": "pending",
    "total_cents": 10000,
    "total_currency": "USD",
    "updated_at": "2017-04-19T10:36:10Z",
    "view_url": "https://xplenty.freshbooks.com/view/asdm7dasdzcvnrt71"
  },
  {
    "created_at": "2017-04-12T10:36:10Z",
    "id": 4200,
    "issued_at": "2017-04-12T10:35:26Z",
    "notes": null,
    "number": 312382,
    "status": "successful",
    "total_cents": 10000,
    "total_currency": "USD",
    "updated_at": "2017-04-14T15:42:34Z",
    "view_url": "https://xplenty.freshbooks.com/view/Bsdm7dasdzcvnrt41"
  }
]
```
