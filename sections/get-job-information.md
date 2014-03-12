## Get Job Information

### Description
The calls returns information for a job with the given job ID.

You can preview the output, which will display up to 100 lines, using the preview_url listed in the outputs of the response. 
View [Preview Job Output] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/preview-output.md) for details.

The details returned for the job are:

* **id** - the numeric job ID
* **status** - the job status. Possible values are: 
    * **idle** - the user sent a request to run the job
    * **pending** - the job is initializing
    * **running** - the job is running
    * **completed** - the job completed successfully
    * **failed** - the job failed to complete
    * **pending_stoppage** - the user sent a request to stop the job
    * **stopping** - the job is stopping
    * **stopped** - the job has stopped
* **variables** - a list of the variables supplied to the "run" request
* **owner_id** - the numeric user ID
* **progress** - the job progress in percentages (a value between 0.0 and 1.0)
* **outputs_count** - the number of output targets defined in the job's package
* **outputs** -  list of the output targets defined in the job's package
* **started_at** - the date and time the job started running
* **created_at** - the date and time the "run" request was made
* **failed_at** - the date and time the job failed (if it failed)
* **updated_at** - the date and time the job was last updated (occurs when package tasks are completed)
* **cluster_id** - the ID of the cluster in which the job was run
* **package_id** - the ID of the package that the job ran (or is running)
* **errors** - a textual message describing errors encountered while the job was run
* **url** - the job resource URL
* **runtime_in_seconds** - the time in seconds that the job has run up to the current time
* **completed_at** - the date and time at which the job completed (stopped, failed or completed)

### Input Parameters
The **job resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/jobs/<jobID>"
```

### Response Example
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
            "component_name": "destination1",
            "created_at": "2013-03-04T07:17:51Z",
            "id": 521,
            "name": "projected_results",
            "preview_url": "https://api.xplenty.com/xplentation/api/jobs/157/outputs/521/preview",
            "records_count": 10415234,
            "updated_at": "2013-03-04T07:17:51Z",
            "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521"
        },
        {
            "component_name": "destination2",
            "created_at": "2013-03-04T07:14:44Z",
            "id": 522,
            "name": "projected_results2",
            "preview_url": "https://api.xplenty.com/xplentation/api/jobs/157/outputs/522/preview",
            "records_count": 423,
            "updated_at": "2013-03-04T07:14:44Z",
            "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522"
        },
    ],
    "started_at": "2012-12-30T14:21:29Z",
    "created_at": "2012-12-30T14:21:18Z",
    "failed_at": null,
    "updated_at": "2012-12-30T14:29:29Z",
    "cluster_id": 52,
    "package_id": 434,
    "errors": "",
    "url": "https://api.xplenty.com/xplenation/api/jobs/157",
    "runtime_in_seconds": 417,
    "completed_at": null
}
```
