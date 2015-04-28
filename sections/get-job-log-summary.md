## Get Job Log Summary

### Description
Log summary for an [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md).

### Input Parameters
The **job resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id/log" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "body": "Package failed to execute",
  "url": "https://api.xplenty.com/xplenation/api/jobs/157/log"
}
```
