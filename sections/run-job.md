## Run Job

### Description
This call creates a new job and triggers it to run. The job performs the series of data processing tasks that are defined in the job's package. Unless the job encounters an error or is terminated by the user, it will run until it completes its tasks on all of the input data.

### Notes
* Save the job ID value returned in the response "id" field. You will use the value to refer to this job in subsequent API calls.

### Input Parameters
* **cluster_id** - the ID of the cluster on which to run the job
* **package_id** - the ID of the package whose tasks the job will perform
* **variables** - custom input variables can optionally be defined in the package. If the package has input variables, you can supply their names and values in the run request (see "variables" syntax below).

### Request (Curl Call)
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/jobs" 
	-d "job[cluster_id]=<clusterID>" 
	-d "job[package_id]=<packageID>" 
	-d "job[variables][<VARNAME1>]=<value1>" 
	-d "job[variables][<VARNAME2>]=<value2>"
	-d "job[variables][<VARNAME3>]=<value3>"
	...
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
            "records_count": 10415234,
            "updated_at": "2013-03-04T07:17:51Z",
            "url": "https://api.xplenty.com/xplenation/api/jobs/299/outputs/521",
        },
        {
            "component_name": "destination2",
            "created_at": "2013-03-04T07:14:44Z",
            "id": 522,
            "name": "projected_results2",
            "records_count": 423,
            "updated_at": "2013-03-04T07:14:44Z",
            "url": "https://api.xplenty.com/xplenation/api/jobs/299/outputs/522",
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
```
