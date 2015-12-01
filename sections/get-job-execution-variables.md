## Get Job Execution Variables

### Description
List all [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md) variables  that were used during job runtime.

### Input Parameters
The **account resource ID** and **job resource ID** must be supplied in the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id/variables" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "variables": {
    "some_variable": 32,
    "other_variable": "test"
  },
  "url": "https://api.xplenty.com/sample-account/api/jobs/1/variables"
}
```
