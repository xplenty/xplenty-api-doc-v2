### Sftp Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`swift`
|name|N|Y| |the descriptive name given to the connection
|username|N|Y| |the SFTP server user name
|password|N|Y| |the SFTP server password. Required only for Password Authentication method
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|host|N|N| |the name of the SFTP server to connect to
|port|N|N|22|the TCP Port to connect to
|auth_method|N|N|"password"|the authentication method to use. Possible values: **password**, **key**
|url|Y| | |the connection resource URL (API)
