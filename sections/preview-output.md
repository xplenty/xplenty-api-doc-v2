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
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/jobs/<jobID>/outputs/<outputID>/preview"
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
