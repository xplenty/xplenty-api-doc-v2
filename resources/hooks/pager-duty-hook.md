An Xplenty **PagerDuty hook** is kind of notification that will be fired as a PagerDuty alert message when state of resource ([cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) or [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md)) is changed. Types of notifications can be specified with **events** variable.

### PagerDuty Hook Attributes

* **id** - the numeric hook ID
* **type** - `pagerduty`
* **active** - indicates whether the PagerDuty hook is active
* **settings** - settings specific for the PagerDuty hook. It contains the following attributes:
  * **pd_account** - PagerDuty account
  * **service_name** - name of the PagerDuty service
  * **service_key** - key of the PagerDuty service
* **events** - list of notification events. Possible values:
  * **job** - all job events
  * **job.submitted**
  * **job.started**
  * **job.stopped**
  * **job.completed**
  * **job.failed**
  * **cluster** - all cluster events
  * **cluster.requested**
  * **cluster.available**
  * **cluster.terminated**
  * **cluster.idled**
  * **cluster.error**
