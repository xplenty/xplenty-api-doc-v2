## Get Job Information

### Description
Info for an existing [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md).

You can preview the output, which will display up to 100 lines, using the preview_url listed in the outputs of the response. 
View [Preview Job Output](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/preview-output.md) for details.

### Input Parameters
* The **job resource ID** must be supplied at the end of the request URL.
* **include** (optional) - Additional information to include in the response:
  * `log_summary` - Includes detailed log information and error analysis for the job

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

To include log summary:
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id?include=log_summary" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 157,
  "status": "completed",
  "variables": {},
  "owner_id": 1,
  "progress": 1,
  "outputs_count": 2,
  "outputs": [
    {
      "component": {
        "name": "destination7",
        "type": "cloud_storage_destination_component",
        "fields": [
          "id",
          "account_name"
        ]
      },
      "created_at": "2013-03-04T07:17:51Z",
      "id": 521,
      "name": "projected_results",
      "preview_url": "https://api.xplenty.com/xplentation/api/jobs/157/outputs/521/preview",
      "records_count": 10415234,
      "updated_at": "2013-03-04T07:17:51Z",
      "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521"
    },
    {
      "component": {
        "name": "destination7",
        "type": "cloud_storage_destination_component",
        "fields": [
          "id",
          "account_name"
        ]
      },
      "created_at": "2013-03-04T07:14:44Z",
      "id": 522,
      "name": "projected_results2",
      "preview_url": "https://api.xplenty.com/xplentation/api/jobs/157/outputs/522/preview",
      "records_count": 423,
      "updated_at": "2013-03-04T07:14:44Z",
      "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522"
    }
  ],
  "started_at": "2012-12-30T14:21:29Z",
  "created_at": "2012-12-30T14:21:18Z",
  "failed_at": null,
  "updated_at": "2012-12-30T14:29:29Z",
  "cluster_id": 52,
  "package_id": 434,
  "errors": "",
  "runtime_in_seconds": 417,
  "completed_at": null,
  "url": "https://api.xplenty.com/xplenation/api/jobs/157",
  "html_url": "https://xplenty.com/xplenation/jobs/157",
  "log_url": "https://api.xplenty.com/xplenation/api/jobs/157/log",
  "creator":
  {
      "type":"Schedule",
      "id":1,
      "display_name": "Schedule 1",
      "url": "https://api.xplenty.com/xplenation/api/schedules/1",
      "html_url": "https://xplenty.com/xplenation/schedules/1"
  }
}
```

When including log_summary, the response will contain an additional `log_summary` object:

```json
{
  "log_summary": {
    "id": 1122631,
    "body": "...",
    "error_summary": "Customer ID missing",
    "openai_extract": "Failed to send request: I/O exception: Request returned an error: com.netledger.schemabean.NLSchemaBeanException: id not found on {urn:relationships_2021_2.lists.webservices.netsuite.com}Customer",
    "action_items": [
      "Validate the Customer ID.",
      "Retry the job."
    ],
    "created_at": "2025-01-15T13:34:41Z"
  }
}
```
