## Xplenty Typical Workflow

These are the steps of a typical workflow for running a job using the Xplenty API, after [defining a package using the Xplenty web application](http://community.xplenty.com/knowledgebase/articles/184931-xplenty-s-packages) and determining the required cluster size. You may want to repeat this workflow on a recurring basis, for instance every day or every week, depending on the rate that your data accumulates.

* [Step 1: Create a Cluster](#CreateCluster)
* [Step 2: Verify Cluster Initialization](#VerifyCluster)
* [Step 3: Run a Job](#RunJob)
* [Step 4: Verify Job Initialization](#VerifyJob)
* [Step 5: Monitor Job Status Until Completion](#MonitorJob)
* [Step 6: Preview Job Output] (#PreviewJob)
* [Step 7: Run Additional Jobs (Optional)](#RunMoreJobs)
* [Step 8: Terminate the Cluster](#TerminateCluster)
* [Step 9: Verify Cluster Termination](#VerifyClusterTermination)

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

View [Create Cluster] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/create-cluster.md) for the details of the request and response

***
<a name="VerifyCluster" id="VerifyCluster">
### Step 2: Verify Cluster Initialization
</a>
Poll the cluster status and check its status value. When the status changes to "available", the cluster has finished initializing and is ready to run jobs. When requesting cluster information, the cluster ID must appear at the end of the cluster URL.

**Request**
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/clusters/167"
```

View [Get Cluster Information] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-cluster-information.md) for details of the response.

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

View [Run Job] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/run-job.md) for details of the request and response.

***
<a id="VerifyJob" name="VerifyJob">
### Step 4: Verify Job Initialization
</a>
Poll the job status and check its status value. When the status changes to "running", the job has been successfully launched. When requesting job information, the job ID must appear at the end of the job URL.

**Request**
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/jobs/305"
```

View [Get Job Information] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-job-information.md) for details of the response.

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

View [Get Job Information] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-job-information.md) for details of the response.

***
<a id="PreviewJob" name="PreviewJob">
### Step 6: Preview Job Output
</a>
Optionally preview the output, which will display up to 100 lines. When requesting job output, the job ID and output id must must be supplied in the request URL.

**Request**
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/jobs/305/outputs/4160/preview"
```

View [Preview Job Output] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/preview-output.md) for details of the response.

***

<a id="RunMoreJobs" name="RunMoreJobs">
### Step 7: Run Additional Jobs (Optional)
</a>
Optionally, repeat steps 3, 4 and 5, to run additional jobs for other data or other packages.

***
<a id="TerminateCluster" name="TerminateCluster">
### Step 8: Terminate the Cluster
</a>
Request to terminate the cluster, releasing its resources.

**Request**
```shell
    curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/clusters/167"
```

View [Terminate Cluster] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/terminate-cluster.md) for details of the response.

***
<a id="VerifyClusterTermination" name="VerifyClusterTermination">
### Step 9: Verify Cluster Termination
</a>
Poll the cluster status and check its status value. When the status changes to "terminated", the cluster resources have been released.
When requesting cluster information, the cluster ID must appear at the end of the cluster URL.

**Request**
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u V4eyfgNqYcSasXGhzNxS: "https://api.xplenty.com/xplenation/api/clusters/167"
```

View [Get Cluster Information] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/get-cluster-information.md) for details of the response.
