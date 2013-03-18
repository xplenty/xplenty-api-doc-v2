The Xplenty jar is a Java artifact that provides a simple wrapper for the Xplenty REST API. 
To use it, create an XplentyAPI object and call its methods to access the Xplenty API.
This page describes the available XplentyAPI methods.

### Create an XplentyAPI Object

Pass your account ID and API key to the XplentyAPI constructor.

    String account_id = "MyAccountID";
    String api_key = "V4eyfgNqYcSasXGhzNxS";
    XplentyAPI xplentyAPI = new XplentyAPI(account_id , api_key);

### List the Cluster Plans

A cluster plan is a definition of a cluster type, which includes the number of nodes in the cluster and its pricing. Cluster plan details can be viewed in the Xplenty web application.
After you've determined which cluster plan is appropriate for your needs, use this method to retrieve the cluster plan ID. The cluster plan ID can then be used when creating a new cluster.

    List<ClusterPlan> clusterPlans = xplentyAPI.listClusterPlans();
    Iterator it = clusterPlans.iterator();
    while(it.hasNext())
    {
      ClusterPlan plan = (ClusterPlan)it.next();
      long clusterPlanId = plan.getId();
    }

### Create a Cluster

This method creates a new cluster. A cluster is a group of machines ("nodes") allocated to your account. The number of nodes in the cluster is determined by the "plan_id" value that you supply to the call. While the cluster is active, only your account's users can run jobs on the cluster.
You will need to provide an active cluster when starting a new job. Save the cluster ID value returned in the response "id" field. You will use the value to refer to this cluster in subsequent API calls.

    long plan_id = 1;
    String name = "New Cluster #199999";
    String description = "New Cluster's Description";
    Cluster cluster = xplentyAPI.createCluster(plan_id, name, description);
    long cluster_id = cluster.getId();

### List All Clusters

This method returns the list of clusters that were created by users in your account.
You can use this information to monitor and display your clusters and their statuses.

    List<Cluster> clusters = xplentyAPI.listClusters();
    Iterator it = clusters .iterator();
    
    while(it.hasNext())
    {
      Cluster cluster = (Cluster)it.next();
      String name = cluster.getName();
      long id = cluster.getId();
    }

### Get Cluster Information

This method returns the details of the cluster with the given ID.

    long id = 85;
    Cluster cluster = xplentyAPI.clusterInformation(id);
    String cluster_name = cluster.getName();

### Terminate a Cluster

This method deactivates the given cluster, releasing its resources and terminating its runtime period. Use this method when all of the cluster's jobs are completed and it's no longer needed. The method returns the given cluster's details, including a status of "pending_terminate".

    long id = 85;
    Cluster cluster = xplentyAPI.terminateCluster(id);
    ClusterStatus status = cluster.getStatus();

### Run a Job

This method creates a new job and triggers it to run. The job performs the series of data processing tasks that are defined in the job's package. Unless the job encounters an error or is terminated by the user, it will run until it completes its tasks on all of the input data. Save the job ID value returned in the response "id" field. You will use the value to refer to this job in subsequent API calls.

    long cluster_id = 83;
    long package_id = 782;
    Map<String, String> variables = new Map<String, String>();
    variables.put("OUTPUTPATH", "test/job_vars.csv");
    variables.put("Date", "09-10-2012");
    
    Job job = xplentyAPI.runJob(cluster_id, package_id, variables);
    
    long id = job.getId();

### List All Jobs

This method returns information for all the jobs that have been created under your account.

    List<Job> jobs = xplentyAPI.listJobs();

    Iterator it = jobs.iterator();
    
    while(it.hasNext())
    {
      Job job = (Job)it.next();
      long id = job.getId();
      JobStatus status = job.getStatus();
      Double progress = job.getProgress();
    }

### Get Job Information

This method retrieves information for a job, according to the given job ID.

    long job_id = 235;
    Job job = xplentyAPI.jobInformation(job_id);
    JobStatus status = job.getStatus();

### Terminate a Job

This method terminates an active job. Usually it's unnecessary to request to terminate a job, because normally the job will end when its tasks are completed. You may want to actively terminate a job if you need its cluster resources for a more urgent job, or if the job is taking too long to complete.

    long job_id = 235;
    Job job = xplentyAPI.stopJob(job_id);
    JobStatus status = job.getStatus();
