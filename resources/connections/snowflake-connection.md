### Snowflake Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`snowflake`
|name|N|Y| |the descriptive name given to the connection
|account_name|N|Y| |the name of your account (provided by Snowflake)
|username|N|Y| |the database user name
|password|N|Y| |the database user password
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|database|N|N| |the name of database to use
|warehouse|N|Y| |the name of warehouse to use
|region|N|N| |the [geographical location](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-regions.md) of your Snowflake cluster (e.g `snowflake::us-east-1`)
|tunnel_type|N|N|"direct"|the method to use for accessing the database. Possible values: **direct**, **reverse**. In case of **reverse** type, **host** will be empty.
|url|Y| | |the connection resource URL (API)
