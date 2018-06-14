### Amazon Athena Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`athena`
|name|N|Y| |the descriptive name given to the connection
|username|N|Y| |IAM Access Key ID
|password|N|Y| |IAM Secret Access Key
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|s3_staging_dir|N|Y| |the path of the Amazon S3 location to store query results, prefixed by `s3://`
|region|N|Y| |the [geographical location](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-regions.md) of your Amazon Athena instance (e.g `amazon-web-services::us-east-1`)
|tunnel_type|N|N|"direct"|the method to use for accessing the database. Possible values: **direct**, **reverse**. In case of **reverse** type, **host** will be empty.
|url|Y| | |the connection resource URL (API)
