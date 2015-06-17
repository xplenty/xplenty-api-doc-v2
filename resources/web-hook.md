An Xplenty **web hook** is kind of notification that will be fired as a HTTP request to specified URL when state of resource ([cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) or [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md)) is changed. Types of notifications can be specified with **events** variable.
Notification request contains hash which is generated using SHA-1 from string created by concatenation of the following fields:

* **id**
* **event name**
* **url**
* **salt**

Notified application can verify with **salt** if request was sent by Xplenty.

### Web Hook Attributes

* **id** - the numeric hook ID
* **active** - indicates whether the web hook is active
* **basic_auth** - indicates whether the basic authentication is required
* **basic_auth_data** - data needed for basic authentication (user:password encoded with base64)
* **insecure_ssl** - indicated whether SSL certificate is verified
* **salt** - salt needed for verification
* **events** - list of notification events. Possible values:
  * **job** - all job events
  * **job.created**
  * **job.started**
  * **job.stopped**
  * **job.completed**
  * **job.failed**
  * **cluster** - all cluster events
  * **cluster.created**
  * **cluster.available**
  * **cluster.terminated**
  * **cluster.idled**
  * **cluster.error**
