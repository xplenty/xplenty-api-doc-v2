An Xplenty **Hip Chat hook** is kind of notification that will be fired as a Hip Chat message to specified room when state of resource ([cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) or [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md)) is changed. Types of notifications can be specified with **events** variable.

### Hip Chat Hook Attributes

* **id** - the numeric hook ID
* **type** - `hipchat`
* **name** - name of the hook, default: value of `room` field (from `settings`)
* **active** - indicates whether the Hip Chat hook is active
* **settings** - settings specific for the Hip Chat hook. It contains the following attributes:
  * **room** - ID of the Hip Chat room
  * **auth_token** - Hip Chat API token
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
* **salt** - hash generated using SHA-1 from string created by concatenation of the following fields:
  * **id**
  * **event name**
  * **url**
  * **salt**
