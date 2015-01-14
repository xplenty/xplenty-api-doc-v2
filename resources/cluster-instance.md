An Xplenty **cluster instance** is a machine (node) that were allocated for a given cluster.

### Cluster Instance Attributes

* **instance_id** - the provider specific identifier of the instance
* **private_dns** - the private fully qualified DNS of the instance
* **public_dns** - the public fully qualified DNS of the instance
* **status** - the instance's status. Possible values are:
    * **available** - the instance is available
    * **terminated** - the instance is no longer accessible
* **master** - indicates whether the instance is the master of the cluster
* **spot** - indicates whether the instance is a spot instance
