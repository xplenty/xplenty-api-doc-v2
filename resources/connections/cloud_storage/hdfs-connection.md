### Hadoop Distributed File System Connection Attributes

* **id** - the connection's numeric identifier
* **type** - `hdfs`
* **name** - the descriptive name given to the connection
* **username** - the Hadoop user name
* **unique_id** - the unique connection's identifier
* **created_at** - the date and time the connection was created
* **updated_at** - the date and time the connection was last updated
* **properties** - Individual connection properties:
  * **name_node_host** - the name of the NameNode host to connect to
  * **name_node_port** - the TCP Port of the NameNode to connect to. Leave blank if cluster HDFS High Availability (HA) is enabled. Common values are 8020 or 9000
  * **httpfs_host** - the name of the Hadoop HDFS gatweay node to connect to
  * **httpfs_port** - The TCP Port of the Hadoop HDFS gatweay node to connect to. Default is 14000
