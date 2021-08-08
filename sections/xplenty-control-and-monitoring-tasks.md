# Xplenty Control and Monitoring Tasks
 
These are the main tasks you can perform with the Xplenty control and monitoring API.

## Cluster Management
The most common way to manage clusters is to [create a cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/create-cluster.md) when you need to run one or more jobs, and [terminate the cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/terminate-cluster.md) when the jobs are completed. 
When you create a cluster, you either specify it's a sandbox type cluster with one node or specify the number of compute nodes when it's a production type cluster.

After creating a cluster, poll its status by [retrieving the cluster information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-cluster-information.md) and checking its status value. When the status changes to "available", the cluster has finished initializing and is ready to run jobs.

You can also [update the cluster information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/update-cluster.md), including modifying the number of compute nodes in the cluster.

After terminating a cluster, poll its status and verify that it has changed to "terminated", to ensure that its resources have been released.

## Job Management
To process your data according to the Xplenty package you defined, you will need to [run a job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/run-job.md). When you submit the job request, you pass values for the custom variables you have defined in the package the job is running. Usually these will include (at least) values that determine which data will be processed and where to write the job's output. For example, you may define that the job should process certain S3 folders and that the output should be written to a different S3 folder every day. In this case, you'll need to pass the folder names in job variables when calling the run request.

Normally the job will end when its tasks are completed, and there is no need to terminate the job via the API. Although you can run several jobs on the same cluster, you may want to actively [terminate a job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/terminate-job.md) if you need its cluster resources for a more urgent job, or if the job is taking too long to complete. 

After terminating a job, poll its status by [retrieving the job's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-information.md) and verify that it has changed to "stopped", to ensure that its resources have been released.

After requesting to run a job, poll its status by [retrieving the job's information](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-information.md) and checking its status value. When the status changes to "running", the job has been successfully launched. Continue to monitor a job's status while it runs, so that you can:
* Determine when a job has finished (its status changes to "completed") 
* Detect and handle failed jobs
* Detect jobs that are taking to long to complete and might need to be terminated 

## Monitoring Jobs and Clusters
You can use the Xplenty monitoring API calls to monitor the progress of your data processing jobs, detect error conditions, and analyze and modify your resource usage. These calls allow you to retrieve information about a [single cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-cluster-information.md), [all clusters](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-clusters.md), a [single job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/get-job-information.md), or [all jobs](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-jobs.md). You can use the cluster information to see which clusters are active, how many jobs they're running and whether they have error conditions. You can use the job information to see which jobs are running, their status, their progress percentage, error conditions, and so on.

Instead of polling job and cluster information to retrieve their status, you can choose to [receive notification messages](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/watch-clusters-and-jobs.md) when jobs and clusters reach certain statuses. These notifications are email messages, or as messages which you can view in the Xplenty web application. You can then manually take the appropriate action.
