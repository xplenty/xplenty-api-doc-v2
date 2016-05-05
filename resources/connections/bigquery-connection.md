### BigQuery database Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`bigquery`
|name|N|Y| |the descriptive name given to the connection
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|database|N|N| |the ID of the dataset to connect to
|host|N|Y| |the ID of the project that contains the dataset to connect to
|region|N|Y| |the geographical location of the dataset to connect to.
|url|Y| | |the connection resource URL (API)
