### Google Cloud Spanner Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`googlecloudspanner`
|name|N|Y| |the descriptive name given to the connection
|username|N|Y| |the database user name
|password|N|Y| |the database user password
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|database|N|Y| |the name of database to use
|host|N|Y| |the ID of the project that contains the instance to connect to
|instance_id|N|Y| |the ID of the instance to connect to
|url|Y| | |the connection resource URL (API)
