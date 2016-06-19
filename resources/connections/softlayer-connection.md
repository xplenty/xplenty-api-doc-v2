### Softlayer Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`softlayer`
|name|N|Y| |the descriptive name given to the connection
|username|N|Y| |the username as defined in the SoftLayer Object Storage account credentials
|password|N|Y| |the API Key (Password) as defined in the SoftLayer Object Storage account credentials
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|region|N|Y| |name of the region
|url|Y| | |the connection resource URL (API)
