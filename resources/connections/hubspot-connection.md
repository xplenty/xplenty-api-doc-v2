### Hubspot Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`hubspot`
|name|N|Y| |the descriptive name given to the connection
|username|N| | |Hubspot user name
|password|N|Y| |Hubspot password. Required only for Password Authentication method
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|owner_id|Y| | |the numeric identifier of the account's owner
|tunnel_type|N| | | the method to use for accessing the database
|local_port|N|N|46126|the TCP Port to connect to
|url|Y| | |the connection resource URL (API)
