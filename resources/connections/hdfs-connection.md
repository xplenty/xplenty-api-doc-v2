### Hadoop Distributed File System Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`hdfs`
|name|N|Y| |the descriptive name given to the connection
|username|N|N| |the Hadoop user name
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|name_node_host|N|Y| |the name of the NameNode host to connect to
|name_node_port|N|N| |the TCP Port of the NameNode to connect to. Leave blank if cluster HDFS High Availability (HA) is enabled. Common values are 8020 or 9000
|httpfs_host|N|Y| |the name of the Hadoop HDFS gateway node to connect to
|httpfs_port|N|N|14000|the TCP Port of the Hadoop HDFS gatweay node to connect to
|url|Y| | |the connection resource URL (API)
