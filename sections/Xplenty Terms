Here are some of the terms you will encounter in the Xplenty API documentation.

## Package

An Xplenty **package** is a data flow definition that you define in the Xplenty web application. 
It describes the data to process (location, schema, fields), data manipulation to perform, and the output destinations (location, schema). The package's workflow is implemented by jobs.

An Xplenty package is a data flow definition that you define in the Xplenty web application. 
## Job
An Xplenty **job** is a process that is responsible for performing a data flow according to a specific package on a Hadoop cluster. The job is a batch process that runs on a finite amount of data and then terminates. Several jobs can run the same package simultaneously.
When you call the Xplenty API to run a new job, you supply the name of the package whose workflow the job should perform, and the cluster on which to run.

## Cluster and Cluster Plan

An Xplenty **cluster** is a Hadoop cluster - a group of machines (nodes) that that is allocated exclusively to your account's users. You can create one or more clusters, and you can run one or more jobs on each cluster. A cluster that you've created remains allocated to your account until you request to terminate the cluster.

A **cluster plan** is a definition of a cluster type, which includes the number of nodes in the cluster and its pricing. Cluster plan details can be viewed in the Xplenty web application. When you create a new cluster, you specify its cluster plan. You  may choose different cluster plans for different types of jobs and packages, depending on the computing power you require.

## Account and User
An Xplenty **account** represents a related group (usually a company) of Xplenty **users**.
An account is created when the user signs up to use the Xplenty service, and an API key is generated for the account, which must be supplied when calling the Xplenty API.
