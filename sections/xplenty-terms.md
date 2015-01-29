## Xplenty Terms

Here are some of the terms you will encounter in the Xplenty API documentation.

### Package

An Xplenty **package** is a data flow definition that you define in the Xplenty web application.
It describes the data to process (location, schema, fields), data manipulation to perform, and the output destinations (location, schema). The package's workflow is implemented by jobs.

An Xplenty package is a data flow definition that you define in the Xplenty web application.

### Job
An Xplenty **job** is a process that is responsible for performing a data flow according to a specific package on a Hadoop cluster. The job is a batch process that runs on a finite amount of data and then terminates. Several jobs can run the same package simultaneously.
When you call the Xplenty API to run a new job, you supply the name of the package whose workflow the job should perform, and the cluster on which to run.

### Cluster

An Xplenty **cluster** is a Hadoop cluster - a group of machines (nodes) that is allocated exclusively to your account's users. You can create one or more clusters, and you can run one or more jobs on each cluster. A cluster that you've created remains allocated to your account until it's terminated.

### Schedule

An Xplenty **schedule** executes packages periodically starting at a specified date and time. The packages will be executed as scheduled, using an existing cluster that fits the scheduled cluster size or, if one doesn't exist, a cluster provisioned automatically with the number of specified nodes. By default, the cluster is taken down as soon as package execution is completed.

### Account and User
An Xplenty **account** represents a related group (usually a company) of Xplenty **users**.
An account is created when the user signs up to use the Xplenty service, and an API key is generated for the account, which must be supplied when calling the Xplenty API.
