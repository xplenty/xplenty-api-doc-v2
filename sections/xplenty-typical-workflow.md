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
$ curl -X POST -u api_key: "https://api.xplenty.com/xplenation/api/clusters" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "nodes":4,
    "type":"production",
    "name":"New Cluster",
    "description":"New Cluster Description"
  }'
```

View [Create Cluster] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-cluster.md) for the details of the request and response

***
<a name="VerifyCluster" id="VerifyCluster">
### Step 2: Verify Cluster Initialization
</a>
Poll the cluster status and check its status value. When the status changes to "available", the cluster has finished initializing and is ready to run jobs. When requesting cluster information, the cluster ID must appear at the end of the cluster URL.

**Request**
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/clusters/:cluster_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

View [Get Cluster Information] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-cluster-information.md) for details of the response.

***
<a id="RunJob" name="RunJob">
### Step 3: Run a Job
</a>
Request to run a new job, passing values for the cluster ID, the package ID, and variables that determine which data will be processed, where the output will be written, and any other custom variables you have defined in the package. 

**_Note:_** Save the job ID value returned in the response "id" field. You will use the value to refer to this job in subsequent API calls.

**Request**
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/jobs" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "cluster_id":167,
    "package_id":103,
    "dynamic_variables":{
      "current_time":"CurrentTime()",
      "MY_CURRENT_TIME":"$CURRENT_TIME_VAR",
      "MY_STRING_VAR":"'some string'"
    },
    "variables": {
      "MY_STATIC_VAR":"some static variable"
    }
  }'
```

View [Run Job] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/run-job.md) for details of the request and response.

### Schedule a Job

A job can be run on a schedule. Create a schedule when jobs should run, specifying the schedule time and days to run, start time and packages. The jobs will then be run per the schedule until the schedule is terminated.

**Note:** When running by schedule, the cluster does not have to be created, as in the previous steps, and can be created automatically with the number of nodes specified.

**Request** 
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/schedules" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name":"Untitled",
    "status":"enabled",
    "start_at":"2014-09-25T08:33:00Z",
    "description":"My daily schedule",
    "interval_amount":34,
    "interval_unit":"days",
    "task": {
      "nodes":4,
      "terminate_on_idle":true,
      "time_to_idle":60,
      "packages":[
        {
          "package_id": "1234",
          "variables": {
            "today": "'val1'",
            "yesterday": "'val2'"
          }
        },  
        {
          "package_id": "3456",
          "variables": {
            "today": "'val3'",
            "yesterday": "'val4'"
          }
        }
      ]
    }
  }'
```

View [Create Schedule] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-schedule.md) for details of the request and response.

***
<a id="VerifyJob" name="VerifyJob">
### Step 4: Verify Job Initialization
</a>
Poll the job status and check its status value. When the status changes to "running", the job has been successfully launched. When requesting job information, the job ID must appear at the end of the job URL.

**Request**
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

View [Get Job Information] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-information.md) for details of the response.

***
<a id="MonitorJob" name="MonitorJob">
### Step 5: Monitor Job Status Until Completion
</a>
Continue to monitor the job's status while it runs, by retrieving job information periodically. When requesting job information, the job ID must appear at the end of the job URL.

Check the value of the job's "status" field. When it changes to "completed" or "failed", send a notification of the completion status and any errors encountered (retrieve error descriptions from the "errors" field).

**Request**
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

View [Get Job Information] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-information.md) for details of the response.

***
<a id="PreviewJob" name="PreviewJob">
### Step 6: Preview Job Output
</a>
Optionally preview the output, which will display up to 100 lines. When requesting job output, the job ID and output id must must be supplied in the request URL.

**Request**
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/jobs/:job_id/outputs/:output_id/preview" \
  -H "Accept: application/vnd.xplenty+json"
```

View [Preview Job Output] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/preview-output.md) for details of the response.

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
$ curl -X DELETE -u api_key: "https://api.xplenty.com/:account_id/api/clusters/:cluster_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

View [Terminate Cluster] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/terminate-cluster.md) for details of the response.

***
<a id="VerifyClusterTermination" name="VerifyClusterTermination">
### Step 9: Verify Cluster Termination
</a>
Poll the cluster status and check its status value. When the status changes to "terminated", the cluster resources have been released.
When requesting cluster information, the cluster ID must appear at the end of the cluster URL.

**Request**
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/clusters/:cluster_id" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

View [Get Cluster Information] (https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-cluster-information.md) for details of the response.
