### Rackspace Cloud Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`rackspace`
|name|N|Y| |the descriptive name given to the connection
|username|N|Y| |the username as defined in the Rackspace Cloud Files account credentials
|password|N|Y| |the API Key (Password) as defined in the Rackspace Cloud Files account credentials
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|region|N|Y| |name of the region
|auth_type|N|N|"apikey"|the type of authentication. Possible values: **apikey**, **password**, **accesskey**
|url|Y| | |the connection resource URL (API)
