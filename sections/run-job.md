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
	"id": 305,
	"status": "pending",
	"variables": 
	{
		"InputPath": "/today"
	},
	"owner_id": 1,
	"progress": 0,
	"outputs_count": 0,
	"started_at": null,
	"created_at": "2013-03-04T08:10:42Z",
	"updated_at": "2013-03-04T08:10:42Z",
	"cluster_id": 176,
	"package_id": 103,
	"errors": null,
	"url": "https://api.xplenty.com/xplenation/api/jobs/305",
	"runtime_in_seconds": 0
}
```
