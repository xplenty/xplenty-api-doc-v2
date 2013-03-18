The Xplenty PY is a python artifact that provides a simple wrapper for the Xplenty REST API. To use it, create an XplentyClient object and call its methods to access the Xplenty API. This page describes the available XplentyClient methods.

### Create an Xplenty Client Object
Pass your account ID and API key to the XplentyClient constructor.

    from xplenty_api import XplentyClient
    account_id ="MyAccountID"
    api_key = "V4eyfgNqYcSasXGhzNxS"
    client = XplentyClient(account_id,api_key)

### List the Cluster Plans

A cluster plan is a definition of a cluster type, which includes the number of nodes in the cluster and its pricing. Cluster plan details can be viewed in the Xplenty web application.
After you've determined which cluster plan is appropriate for your needs, use this method to retrieve the cluster plan ID. The cluster plan ID can then be used when creating a new cluster.

    plans = client.plans
    for plan in plans:
        print plan.id , plan.name

### Create a Cluster

This method creates a new cluster. A cluster is a group of machines ("nodes") allocated to your account. The number of nodes in the cluster is determined by the "plan_id" value that you supply to the call. While the cluster is active, only your account's users can run jobs on the cluster.
You will need to provide an active cluster when starting a new job. Save the cluster ID value returned in the response "id" field. You will use the value to refer to this cluster in subsequent API calls.

    plan_id = 1
    name ="New Cluster #199999"
    description ="New Cluster's Description"
    cluster = client.create_cluster(plan_id, name, description)
    print cluster.id

### List All Clusters

This method returns the list of clusters that were created by users in your account.
You can use this information to monitor and display your clusters and their statuses.

    clusters = client.clusters
    print "Number of clusters:",len(clusters)
    for cluster in clusters:
        print cluster.id, cluster.name, cluster.created_at

### Get Cluster Information

This method returns the details of the cluster with the given ID.

    id = 85
    cluster = client.get_cluster(id)
    print cluster.name

### Terminate a Cluster

This method deactivates the given cluster, releasing its resources and terminating its runtime period. Use this method when all of the cluster's jobs are completed and it's no longer needed. The method returns the given cluster's details, including a status of "pending_terminate".

    id = 85
    cluster = client.terminate_cluster(id)
    print cluster.status

### Run a Job

This method creates a new job and triggers it to run. The job performs the series of data processing tasks that are defined in the job's package. Unless the job encounters an error or is terminated by the user, it will run until it completes its tasks on all of the input data. Save the job ID value returned in the response "id" field. You will use the value to refer to this job in subsequent API calls.

    cluster_id = 83
    package_id = 782
    variables = {}
    variables['OUTPUTPATH']="test/job_vars.csv"
    variables['Date']="09-10-2012"
    
    job = client.add_job(cluster_id, package_id, variables)
    
    print job.id 

### List All Jobs

This method returns information for all the jobs that have been created under your account.

    jobs = client.jobs

    for job in jobs:
        print job.id , job.progress , job.status

### Get Job Information

This method retrieves information for a job, according to the given job ID.

    job_id = 235
    job = client.get_job(job_id)
    print job.status

### Terminate a Job

This method terminates an active job. Usually it's unnecessary to request to terminate a job, because normally the job will end when its tasks are completed. You may want to actively terminate a job if you need its cluster resources for a more urgent job, or if the job is taking too long to complete.

    job_id = 235
    job = client.stop_job(job_id)
    print job.status
