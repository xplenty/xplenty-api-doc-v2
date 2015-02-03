## List Jobs

### Description
This call returns information for the list of jobs that were created by users in your account.
You can use this information to monitor your jobs and their status.
Optionally, you can supply the input parameters to filter the job list so that it contains only jobs with a specific status, and to determine the order by which the list will be sorted.

The details returned for each job are:

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
* **outputs** - list of the output targets defined in the job's package
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

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
status|N|"all"|Possible values are any status listed above or ```all```. The call will return only jobs with the given status, or all the clusters if the "all" value is specified.
sort|N|"created"|Possible values are ```updated``` or ```created```. The job list will be sorted by the jobs' "updated_at" or "created_at" value respectively.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The jobss will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The job list will only contain jobs updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/jobs?status=<statusFilter>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
```
### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 304,
    "status": "failed",
    "variables":
    {
        "InputPath": "'/today'"
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
        "preview_url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521/preview",
        "records_count": 10415234,
        "updated_at": "2013-03-04T07:17:51Z",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/521"
      },
      {
        "component_name": "destination2",
        "created_at": "2013-03-04T07:14:44Z",
        "id": 522,
        "name": "projected_results2",
        "preview_url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522/preview",
        "records_count": 423,
        "updated_at": "2013-03-04T07:14:44Z",
        "url": "https://api.xplenty.com/xplenation/api/jobs/157/outputs/522"
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
