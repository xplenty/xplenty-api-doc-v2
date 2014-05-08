## Create Cluster

### Description
This call creates a new cluster. A cluster is a group of machines ("nodes") allocated to your account. The number of nodes in the cluster is determined by the "nodes" value that you supply to the call. While the cluster is active, only your account's users can run jobs on the cluster.
You will need to provide an active cluster when [starting a new job](https://github.com/xplenty/xplenty-api-doc/blob/master/sections/run-job.md).

A successful call returns the following details for the new cluster:
