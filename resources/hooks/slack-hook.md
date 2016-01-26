An Xplenty **Slack hook** is kind of notification that will be fired as a Slack message to specified channel when state of resource ([cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) or [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md)) is changed. Types of notifications can be specified with **events** variable.

### Slack Hook Attributes

* **id** - the numeric hook ID
* **type** - `slack`
* **name** - name of the hook, default: concatenation of `team` and `channel` fields (from `settings`) or value of `url` fields if `team` and `channel` are empty
* **active** - indicates whether the Slack hook is active
* **settings** - settings specific for the Slack hook. It contains the following attributes:
  * **url** - URL containing unique token which allows to send messages on the Slack channel.
  * **team** - Slack team
  * **channel** - Slack channel
  * **username** - Slack username
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
