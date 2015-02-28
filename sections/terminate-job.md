## Terminate Job

### Description
This call terminates an active [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md). Usually it's not necessary to request to terminate a job, because the job will end when its tasks are completed. You may want to actively terminate a job if you need its cluster resources for a more urgent job, or if the job is taking too long to complete.

### Notes
* This call only triggers the job's termination, which is why a status of "pending_stoppage" is returned. To verify stoppage, [get the job's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-information.md) and check for a status of "stopped".
* If a job is stopped by the user, it may return only partial results or none at all, depending on its tasks and its stage at the time of stoppage.

### Input Parameters
The **job resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id": 305,
  "status": "pending_stoppage",
  "variables": 
  {
    "InputPath": "'/today'"
  },
  "owner_id": 1,
  "progress": 0,
  "outputs_count": 0,
  "started_at": "2013-03-04T08:10:48Z",
  "created_at": "2013-03-04T08:10:42Z",
  "updated_at": "2013-03-04T08:11:27Z",
  "failed_at": null,
  "cluster_id": 176,
  "package_id": 103,
  "errors": null,
  "url": "https://api.xplenty.com/xplenation/api/jobs/305",
  "runtime_in_seconds": 40,
  "completed_at": null
}
```