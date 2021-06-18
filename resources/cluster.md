An Xplenty **cluster** is a group of machines (nodes) that is allocated exclusively to your account's users. You can create one or more clusters, and you can run one or more jobs on each cluster. A cluster that you've created remains allocated to your account until it's terminated.

You will need to provide an active cluster when [starting a new job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/run-job.md).

### Cluster Attributes

* **id** - the cluster's numeric identifier
* **name** - the name given to the cluster upon creation
* **description** - the description given to the cluster upon creation
* **status** - the cluster's status. Possible values are:
    * **pending** - the cluster is pending creation
    * **creating** - the cluster is being created
    * **available** - the cluster is available
    * **idle** - the cluster is idle
    * **error** - the cluster is in erroneous state
    * **pending_terminate** - the cluster is pending termination
    * **terminating** - the cluster is being terminated
    * **terminated** - the cluster is terminated
* **owner_id** - the numeric user ID of the cluster's owner
* **plan_id** - the ID of the cluster's plan
* **nodes** - the number of compute nodes for the cluster
* **type** - the type of the cluster ("sandbox" or "production")
* **created_at** - the date and time the cluster was created
* **updated_at** - the date and time the cluster was last updated
* **available_since** - the date and time the cluster became available
* **terminated_at** - the date and time the cluster was terminated
* **running_jobs_count** - the number of jobs currently running on the cluster
* **terminate_on_idle** - indicates whether the cluster will be terminated after it becomes idle
* **time_to_idle** - the time interval (in seconds) in which the cluster will become idle
* **idle_since** - the time since cluster changed status to idle
* **terminated_on_idle** - indicates whether the cluster terminated because it became idle
* **region** - the region in which the cluster was created
* **master_instance_type** - the type of the master instance
* **slave_instance_type** - the type of the slave instance
* **master_spot_price** - the maximum bid price (in USD) requested for master spot instance
* **slave_spot_price** - the maximum bid price (in USD) requested for slave spot instance
* **master_spot_percentage** - the percentage of master instances requested as spot (value between 0 and 1)
* **slave_spot_percentage** - the percentage of slave instances requested as spot (value between 0 and 1)
* **allow_fallback** - indicates whether instances will be created as on-demand instances if spot requests are not fulfilled
* **url** - the cluster resource URL (API)
* **html_url** - the cluster resource URL (Web UI)
* **creator** - information about resource which created the job. It contains the following values:
  * **type** - the type of the resource (e.g. Schedule)
  * **id** - the numeric resource ID
  * **url** - the resource URL (API)
  * **html_url** - the resource URL (Web UI)
* **stack** - the stack of the cluster. Possible values are:
  * **vanila-everest**
* **bootstrap_actions** - the array of the custom bootstrap actions. Each of elements contains the following attributes:
  * **script_path** - the path of the bootstrap action script
  * **args** - the array of script parameters. It is an optional field.
