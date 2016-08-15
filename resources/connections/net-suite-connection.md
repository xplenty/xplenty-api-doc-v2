### NetSuite Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`netsuite`
|name|N|Y| |the descriptive name given to the connection
|username|N|Y| |the NetSuite user name
|password|N|Y| |the NetSuite user password
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|database|N|N|"NetSuite.com"|the name of the service data source to use
|host|N|Y| |the name of the host to connect to
|port|N|N|1708|the TCP Port to connect to
|net_suite_account_id|N|Y| |the ID of a company account that can be accessed by the specified User
|role_id|N|N| |the role ID for the use, which determines the privileges
|url|Y| | |the connection resource URL (API)
