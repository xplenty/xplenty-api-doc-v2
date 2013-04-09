## Get Job Information

### Description
The calls retrieves information for a job, according to the given job ID.

The details returned for the job are as follows:

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
* **started_at** - the date and time at which the job started running
* **created_at** - the date and time at which the "run" request was made
* **failed_at** - the date and time at which the job failed (if it failed)
* **updated_at** - the date and time the job was last updated (occurs when package tasks are completed)
* **cluster_id** - the ID of the cluster in which the job was run
* **package_id** - the ID of the package that the job ran (or is running)
* **errors** - a textual message describing errors encountered while the job was run
* **url** - the job resource URL
* **runtime_in_seconds** - the time in seconds that the job has run up to the current time

### Input Parameters
The **job resource ID** must be supplied at the end of the request URL.

### Request (Curl Call)
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/jobs/<jobID>"
```

### Response Example
```json
    {
        "id": 304,
        "status": "failed",
        "variables": 
        {
            "InputPath": "/today"
        },
        "owner_id": 1,
        "progress": 0,
        "outputs_count": 0,
        "started_at": "2013-03-04T08:02:20Z",
        "created_at": "2013-03-04T08:02:17Z",
        "updated_at": "2013-03-04T08:03:01Z",
        "cluster_id": 176,
        "package_id": 103,
        "errors": "Package failed to execute.",
        "url": "https://api.xplenty.com/xplenation/api/jobs/304",
        "runtime_in_seconds": 40
    }
```
