## Import Connection Schema.

### Description
Imports schema of the connection. Xplenty provides tha following types of connections:

* [Bigquery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bigquery-connection.md)
* [Google Cloud SQL Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/googlecloud.md)
* [Hana](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/hana-connection.md)
* [Heroku](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/heroku-connection.md)
* [MongoDB](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mongo-connection.md)
* [MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mysql-connection.md)
* [PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/postgres-connection.md)
* [Redshift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redshift-connection.md)
* [Redis](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redis-connection.md)
* [Segment](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/segment-connection.md)
* [SQL Server](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sqlserver-connection.md)
* [Bingads](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bingads-connection.md)
* [Google Storage](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/gs-connection.md)
* [Google AdWords](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/adwords-connection.md)
* [Google Analytics](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/analytics-connection.md)
* [Hadoop Distributed File System](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/hdfs-connection.md)
* [Rackspace](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/rackspace-connection.md)
* [Amazon S3](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/s3-connection.md)
* [Salesforce](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/salfesforce-connection.md)
* [SSH File Transfer Protoco](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)
* [Softlayer](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/softlayer-connection.md)
* [Swift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/swift-connection.md)

### Input Parameters
The **connection ID** and **connection type**. Possible values of the type are listed above (on the connection types' pages).
There is special case when **connection ID** is not required: when **type** is `curl`.

For the following connection types:

* [Bigquery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bigquery-connection.md)
* [Google Cloud SQL Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/googlecloud.md)
* [Hana](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/hana-connection.md)
* [Heroku](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/heroku-connection.md)
* [MongoDB](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mongo-connection.md)
* [MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mysql-connection.md)
* [PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/postgres-connection.md)
* [Redshift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redshift-connection.md)
* [Redis](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redis-connection.md)
* [Segment](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/segment-connection.md)
* [SQL Server](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sqlserver-connection.md)

you should use these input attributes:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
where_clause|N| |SQL where clause
table|Y| | name of the table
row_count|N|20|row limit
schema_name|N| |

For the following connection types:

* [Bingads](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bingads-connection.md)
* [Google Storage](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/gs-connection.md)
* [Google AdWords](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/adwords-connection.md)
* [Google Analytics](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/analytics-connection.md)
* [Hadoop Distributed File System](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/hdfs-connection.md)
* [Rackspace](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/rackspace-connection.md)
* [Amazon S3](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/s3-connection.md)
* [Salesforce](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/salfesforce-connection.md)
* [SSH File Transfer Protoco](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)
* [Softlayer](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/softlayer-connection.md)
* [Swift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/swift-connection.md)

you should use these input attributes:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
bucket|Y| |bucket or container
path|Y| |path
file_type|N|file|possible **file** or **service**
lines|N|20|lines limit
delimiter|N|\t|
skip_header|N|false|in case of fields name in headers
record_delimiter|N|New line|
record_type|N|Delimited values|
quote|N|none|quotation marks
escape|N| |escape marks

For curl type:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|url|Y| |url for import
|method|Y|"GET"|**GET** or **POST**
|response_type|N|"json"|possible values **raw**, **json**, **array**, **line_delimited_json**
|lines|N|20|
|username|N| |
|password|N| |
|headers|N| |
|body|N| |




### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "/:account_id/api/connections/:connection_type/:connection_id/schema" \
  -H "Accept: application/vnd.xplenty+json; version=2"
  -d '{
    "table":"tableName"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "data": [],
  "raw": [
    "{ \"_id\" : { \"$oid\" : \"5721f8e5d6bfd23191717153\"} , \"item\" : \"card\" , \"qty\" : 15.0}"
  ],
  "fields": [
    {
      "item": "string"
    },
    {
      "qty": "double"
    },
    {
      "_id": "string"
    }
  ]
}
```
