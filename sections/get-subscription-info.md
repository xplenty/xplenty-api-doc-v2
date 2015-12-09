## Get Subscription Information

### Description
Information about current account [subscription](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/subscription.md).

### Input Parameters
The **account resource ID** must be supplied at the beginning of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/subscription" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "trial_period_days":14,
  "plan_id":4,
  "trial_start":"2015-03-13T14:59:25Z",
  "trial_end":"2015-03-27T14:59:25Z",
  "trialling":false,
  "url":"https://api.xplenty.com/xplenty-admin/api/subscription"
}
```
