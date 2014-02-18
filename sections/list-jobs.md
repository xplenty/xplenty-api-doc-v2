## List Jobs

### Description
This call returns information for all the jobs that have been created under your account.
Optionally, you can use the input parameters to filter the job list so that it contains only jobs with a specific status, and to determine the order by which the list will be sorted.

The details returned for each job are as follows:

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
* **completed_at** - the date and time at which the job completed (stopped, failed or completed)

### Input Parameters
* **status** (optional) - Possible values are: ```idle```, ```pending```, ```running```, ```completed```, ```failed```, ```pending_stoppage```, ```stopping```, ```stopped```, ```all``` (default). The call will return only jobs with the given status, or all the jobs if the ```all``` value is specified. 
* **sort** (optional) - Possible values are: ```updated```, ```created``` (default). The job list will be sorted by the jobs' "updated_by" values or "created_by" values respectively, depending on the value of the "sort" parameter.
* **direction** (optional) - Possible values are: ```asc```, ```desc``` (default). The jobs will be sorted in ascending or descending order of the "sort" attribute, depending on the value of "direction".
* **since** (optional) - The job list will be filtered out of any jobs updated before the given time. The time should be passed in as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call)
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" 
    -u <APIkey>: "https://api.xplenty.com/<accountID>/api/jobs?status=<statusFilter>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
```
### Response Example
```json
[
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
        "outputs": [],
        "started_at": "2013-03-04T08:02:20Z",
        "created_at": "2013-03-04T08:02:17Z",
        "updated_at": "2013-03-04T08:03:01Z",
        "failed_at": null,
        "cluster_id": 176,
        "package_id": 103,
        "errors": "Package failed to execute.",
        "url": "https://api.xplenty.com/xplenation/api/jobs/304",
        "runtime_in_seconds": 40,
        "completed_at": "2013-03-04T08:03:01Z"
    },
    {
        "id": 303,
        "status": "failed",
        "variables": {},
        "owner_id": 1,
        "progress": 0,
        "outputs_count": 0,
        "outputs": [],
        "started_at": "2013-03-04T07:38:33Z",
        "created_at": "2013-03-04T07:38:27Z",
        "updated_at": "2013-03-04T07:39:11Z",
        "failed_at": null,
        "cluster_id": 176,
        "package_id": 434,
        "errors": "Package failed to execute.",
        "url": "https://api.xplenty.com/xplenation/api/jobs/303",
        "runtime_in_seconds": 38,
        "completed_at": "2013-03-04T07:39:11Z"
    },
    {
        "id": 299,
        "status": "stopped",
        "variables": {},
        "owner_id": 1,
        "progress": 0,
        "outputs_count": 0,
        "outputs": [],
        "started_at": null,
        "created_at": "2013-03-04T06:58:48Z",
        "updated_at": "2013-03-04T07:17:51Z",
        "failed_at": null,
        "cluster_id": 176,
        "package_id": 434,
        "errors": "Package failed to execute.",
        "url": "https://api.xplenty.com/xplenation/api/jobs/299",
        "runtime_in_seconds": 0,
        "completed_at": "2013-03-04T07:17:51Z"
    },
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
                "records_count": 10415234,
                "updated_at": "2013-03-04T07:17:51Z",
                "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521",
            },
            {
                "component_name": "destination2",
                "created_at": "2013-03-04T07:14:44Z",
                "id": 522,
                "name": "projected_results2",
                "records_count": 423,
                "updated_at": "2013-03-04T07:14:44Z",
                "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522",
            },
        ],
        "started_at": "2012-12-30T14:21:29Z",
        "created_at": "2012-12-30T14:21:18Z",
        "updated_at": "2012-12-30T14:29:29Z",
        "cluster_id": 52,
        "package_id": 434,
        "errors": "",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157",
        "runtime_in_seconds": 417,
        "completed_at": "2012-12-30T14:29:29Z"
    }
]
```
