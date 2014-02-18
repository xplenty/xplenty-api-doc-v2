## Xplenty Typical Workflow

Here are the steps of a typical workflow for running a job using the Xplenty API, after defining a package using the Xplenty web application and determining the required cluster size. You may want to repeat this workflow on a recurring basis, for instance every day or every week, depending on the rate that your data accumulates.

* [Step 1: Create a Cluster](#CreateCluster)
* [Step 2: Verify Cluster Initialization](#VerifyCluster)
* [Step 3: Run a Job](#RunJob)
* [Step 4: Verify Job Initialization](#VerifyJob)
* [Step 5: Monitor Job Status Until Completion](#MonitorJob)
* [Step 6: Run Additional Jobs (Optional)](#RunMoreJobs)
* [Step 7: Terminate the Cluster](#TerminateCluster)
* [Step 8: Verify Cluster Termination](#VerifyClusterTermination)

***
<a id="CreateCluster" name="CreateCluster">
### Step 1: Create a Cluster
</a>
Create a new cluster. The following example creates cluster of type "production" with 2 compute nodes. 

**_Note:_** Save the cluster ID value returned in the response "id" field. You will use the value to refer to this cluster in subsequent API calls.

**Request**
```shell
    curl -X POST -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS:"https://api.xplenty.com/xplenation/api/clusters" 
    -d "cluster[name]=DailyCluster_03032013" 
    -d "cluster[description]=Cluster for running daily jobs. Date 03032013."
    -d "cluster[type]=production" 
    -d "cluster[nodes]=2" 
```

**Response**
```json
    {
        "id": 167,
        "name": "DailyCluster_03032013",
        "description": "Cluster for running daily jobs. Date 03032013.",
        "status": "pending",
        "nodes": 2,
        "type": "production",
        "owner_id": 27,
        "plan_id": 1,
        "created_at": "2013-03-03T13:06:51Z",
        "updated_at": "2013-03-03T13:06:51Z",
        "terminated_at": null,
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/167",
        "terminate_on_idle": false,
        "time_to_idle": 3600
    }
```

***
<a name="VerifyCluster" id="VerifyCluster">
### Step 2: Verify Cluster Initialization
</a>
Poll the cluster status and verify that it changes to the "available" value. When requesting cluster information, the cluster ID must appear at the end of the cluster URL.

**Request**
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/clusters/167"
```

**Response**
```json
    {
        "id": 167,
        "name": "DailyCluster_25072013",
        "description": "Cluster for running daily jobs. Date 03032013.",
        "status": "available",
        "nodes": 2,
        "type": "production",
        "owner_id": 27,
        "plan_id": 1,
        "created_at": "2013-03-03T13:06:51Z",
        "updated_at": "2013-03-03T13:13:19Z",
        "terminated_at": null,
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/167",
        "terminate_on_idle": false,
        "time_to_idle": 3600
    }
```
***
<a id="RunJob" name="RunJob">
### Step 3: Run a Job
</a>
Request to run a new job, passing values for the cluster ID, the package ID, and variables that determine which data will be processed, where the output will be written, and any other custom variables you have defined in the package. 

**_Note:_** Save the job ID value returned in the response "id" field. You will use the value to refer to this job in subsequent API calls.

**Request**
```shell
    curl -X POST -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/jobs" 
    -d "job[cluster_id]=167" 
    -d "job[package_id]=103" 
    -d "job[variables][InputPath]=/input03032013" 
    -d "job[variables][OutputPath]=/output03032013"
```

**Response**
```json
    {
        "id": 305,
        "status": "pending",
        "variables": 
        {
            "InputPath": "/input03032013"
            "OutputPath": "/output03032013"
        },
        "owner_id": 27,
        "progress": 0,
        "outputs_count": 0,
        "outputs": [],
        "started_at": null,
        "created_at": "2013-03-04T08:10:42Z",
        "updated_at": "2013-03-04T08:10:42Z",
        "cluster_id": 167,
        "package_id": 103,
        "errors": null,
        "url": "https://api.xplenty.com/xplenation/api/jobs/305",
        "runtime_in_seconds": 0,
        "completed_at": null
    }
```
***
<a id="VerifyJob" name="VerifyJob">
### Step 4: Verify Job Initialization
</a>
Poll the job's status to verify that it changes to the "running" value. When requesting job information, the job ID must appear at the end of the job URL.

**Request**
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/jobs/305"
```

**Response**
```json
    {
        "id": 305,
        "status": "running",
        "variables": 
        {
            "InputPath": "/input03032013"
            "OutputPath": "/output03032013"
        },
        "owner_id": 27,
        "progress": 5,
        "outputs_count": 0,
        "outputs": [],
        "started_at": "2013-03-03T08:02:20Z",
        "created_at": "2013-03-03T08:02:17Z",
        "updated_at": "2013-03-03T08:03:01Z",
        "cluster_id": 167,
        "package_id": 103,
        "errors": "",
        "url": "https://api.xplenty.com/xplenation/api/jobs/305",
        "runtime_in_seconds": 40,
        "completed_at": null
    }
```
***
<a id="MonitorJob" name="MonitorJob">
### Step 5: Monitor Job Status Until Completion
</a>
Continue to monitor the job's status while it runs, by retrieving job information periodically. When requesting job information, the job ID must appear at the end of the job URL.

Check the value of the job's "status" field. When it changes to "completed" or "failed", send a notification of the completion status and any errors encountered (retrieve error descriptions from the "errors" field).

**Request**
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/jobs/305"
```

**Response**
```json
    {
        "id": 305,
        "status": "running",
        "variables": 
        {
            "InputPath": "/input03032013"
            "OutputPath": "/output03032013"
        },
        "owner_id": 27,
        "progress": 100,
        "outputs_count": 0,
        "outputs": [],
        "started_at": "2013-03-03T08:02:20Z",
        "created_at": "2013-03-03T08:02:17Z",
        "updated_at": "2013-03-03T08:07:01Z",
        "cluster_id": 167,
        "package_id": 103,
        "errors": "",
        "url": "https://api.xplenty.com/xplenation/api/jobs/305",
        "runtime_in_seconds": 200,
        "completed_at": null
    }
```
***
<a id="RunMoreJobs" name="RunMoreJobs">
### Step 6: Run Additional Jobs (Optional)
</a>
Optionally, repeat steps 3, 4 and 5, to run additional jobs for other data or other packages.

***
<a id="TerminateCluster" name="TerminateCluster">
### Step 7: Terminate the Cluster
</a>
Request to terminate the cluster.

**Request**
```shell
    curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/clusters/167"
```

**Response**
```json
    {
        "id": 167,
        "name": "DailyCluster_25072013",
        "description": "Cluster for running daily jobs. Date 03032013.",
        "status": "pending_terminate",
        "nodes": 2,
        "type": "production",
        "owner_id": 27,
        "plan_id": 1,
        "created_at": "2013-03-03T08:02:17Z",
        "updated_at": "2013-03-03T08:07:01Z",
        "available_since": "2013-01-28T16:46:22Z",
        "terminated_at": null,
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/167",
        "terminate_on_idle": false,
        "time_to_idle": 3600
    }
```
***
<a id="VerifyClusterTermination" name="VerifyClusterTermination">
### Step 8: Verify Cluster Termination
</a>
Poll the cluster status and verify that it changes to the "terminated" value. When requesting cluster information, the cluster ID must appear at the end of the cluster URL.

**Request**
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/clusters/167"
```

**Response**
```json
    {
        "id": 167,
        "name": "DailyCluster_25072013",
        "description": "Cluster for running daily jobs. Date 03032013.",
        "status": "terminated",
        "nodes": 2,
        "type": "production",
        "owner_id": 27,
        "plan_id": 1,
        "created_at": "2013-03-03T13:06:51Z",
        "updated_at": "2013-03-03T13:13:19Z",
        "available_since": "2013-01-28T16:46:22Z",
        "terminated_at": "2013-03-03T13:13:19Z",
        "running_jobs_count": 0,
        "url": "https://api.xplenty.com/xplenation/api/clusters/167",
        "terminate_on_idle": false,
        "time_to_idle": 3600
    }
```
