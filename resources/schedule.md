An Xplenty **schedule** executes packages periodically starting at a specified date and time. The packages will be executed as scheduled, using an existing cluster that fits the scheduled cluster size or if one doesn't exist, a cluster will be provisioned automatically with the number of specified nodes. By default, the cluster is taken down as soon as package execution is completed.

### Schedule Attributes

* **id** the numeric schedule ID
* **name** the name given to the schedule upon creation
* **description** the description given to the schedule upon creation
* **owner_id** the numeric user id of the package owner
* **status** the schedule's status. Possible values are:
    * **enabled**
    * **disabled**
* **start_at** the date and time when the schedule should start executing
* **next_run_at** the date and time the schedule's task will run next
* **interval_amount** number of interval units between schedule's task executions
* **interval_unit** Possible values are:
    * **minutes**
    * **hours**
    * **days**
    * **weeks**
    * **months**
    * **years**
* **task**
* **last_run_at** the date and time that schedule's task ran last
* **last_run_status** status of the last execution of the schedule's task
* **execution_count** number of times the schedule has run
* **overlap** allows execution overlapping
* **created_at** the date and time the schedule was created
* **updated_at** the date and time the schedule was updated
* **url** the schedule resource URL (API)
* **html_url** the schedule resource URL (Web UI)
* **reuse_cluster_strategy** the strategy of re-using cluster. Possible values are:
  * **none** do not re-use. It means a new cluster will always be created
  * **self** re-use cluster created by this schedule or create a new one if none was found
  * **any** re-use any cluster with minimal size settings defined in task[nodes] attribute