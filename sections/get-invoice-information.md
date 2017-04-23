## Get Invoice Information

### Description
Information for an existing [invoice](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/invoice.md).

### Input Parameters
The **invoice resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/invoices/:invoice_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
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
}
```
