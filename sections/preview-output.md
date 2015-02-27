## Preview Job Output

### Description
The calls returns up to 100 lines raw preview of the output.

The details returned for the job are as:

* **preview** - preview output
* **url** - the job preview URL

### Input Parameters
The **job resource ID** and **output ID** must be supplied in the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id/outputs/:output_id/preview" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "preview": "appl\t258072",
  "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/4160/preview"
}
```
