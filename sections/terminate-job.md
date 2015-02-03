## Terminate Job

### Description
This call terminates an active job. Usually it's not necessary to request to terminate a job, because the job will end when its tasks are completed. You may want to actively terminate a job if you need its cluster resources for a more urgent job, or if the job is taking too long to complete.

A successful call returns the following details for the given job:

* **id** - the job's numeric identifier
* **status** - the cluster's status, pending_terminate. 
* **variables** - a list of the variables supplied to the "run" request
* **owner_id** - the numeric user ID of the job's owner
* **progress** - the job progress in percentages (a value between 0.0 and 1.0)
* **outputs_count** - the number of output targets defined in the job's package
* **started_at** - the date and time the job started running
* **created_at** - the date and time the "run" request was made
* **updated_at** - the date and time the job was last updated (occurs when package tasks are completed)
* **failed_at** - the date and time the job failed (if it failed)
* **cluster_id** - the ID of the cluster in which the job was run
* **package_id** - the ID of the package that the job ran (or is running)
* **errors** - a textual message describing errors encountered while the job was run
* **url** - the job resource URL
* **runtime_in_seconds** - the time in seconds that the job has run up to the current time
* **completed_at** - the date and time at which the job completed (stopped, failed or completed)

### Notes
* This call only triggers the job's termination, which is why a status of "pending_stoppage" is returned. To verify stoppage, [get the job's information](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-job-information.md) and check for a status of "stopped".
* If a job is stopped by the user, it may return only partial results or none at all, depending on its tasks and its stage at the time of stoppage.

### Input Parameters
The **job resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/jobs/<jobID>"
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
    "InputPath": "/today"
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
