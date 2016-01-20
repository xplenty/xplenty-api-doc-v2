An Xplenty **email hook** is kind of notification that will be fired as a E-mail message to specified address when state of resource ([cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) or [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md)) is changed. Types of notifications can be specified with **events** variable.

### Email Hook Attributes

* **id** - the numeric hook ID
* **type** - `email`
* **active** - indicates whether the email hook is active
* **settings** - settings specific for the email hook. It contains the following attributes:
  * **emails** - Comma-separated list of emails
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
