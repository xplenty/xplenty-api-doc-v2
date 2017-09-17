## Validate Connection

### Description
Checks validation of the Connection. Xplenty provides the following types of connections:

* [BigQuery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bigquery-connection.md)
* [Google Cloud SQL for MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-mysql-connection.md)
* [Google Cloud SQL for PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-postgres-connection.md)
* [Heroku Postgres](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/heroku-postgres-connection.md)
* [MongoDB](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mongo-connection.md)
* [MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mysql-connection.md)
* [PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/postgres-connection.md)
* [Redshift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redshift-connection.md)
* [SQL Server](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sqlserver-connection.md)
* [Bing Ads](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bingads-connection.md)
* [Google Storage](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/gs-connection.md)
* [Google AdWords](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/adwords-connection.md)
* [Google Analytics](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/analytics-connection.md)
* [Hadoop Distributed File System](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/hdfs-connection.md)
* [Amazon S3](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/s3-connection.md)
* [Salesforce](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/salesforce-connection.md)
* [SSH File Transfer Protoco](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)
* [NetSuite](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/net-suite-connection.md)
* [Google Cloud Spanner](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-spanner-connection.md)
* [Oracle Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/oracle-connection.md)
* [Intercom](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/intercom-connection.md)
* [Facebook Ads Insights](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/facebook-ads-insights-connection.md)

### Input Parameters
The **connection ID** and **connection type**. Possible values of the type are listed above (on the connection types' pages).

For the following connection types:

* [BigQuery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bigquery-connection.md)
* [Google Cloud SQL for MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-mysql-connection.md)
* [Google Cloud SQL for PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-postgres-connection.md)
* [Heroku Postgres](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/heroku-postgres-connection.md)
* [MongoDB](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mongo-connection.md)
* [MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mysql-connection.md)
* [PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/postgres-connection.md)
* [Redshift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redshift-connection.md)
* [SQL Server](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sqlserver-connection.md)
* [NetSuite](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/net-suite-connection.md)
* [Google Cloud Spanner](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-spanner-connection.md)
* [Oracle Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/oracle-connection.md)

you should use these input attributes:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
table|N| |name of the table
schema_name|N| |required if table attribute was passed

For the following connection type:
* [Google Analytics](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/analytics-connection.md)

you should use these input attributes:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
profile_ids|Y| |
start_date|Y| |
end_date|Y| |
metrics|N| |
dimensons|N| |
sort|N| |
filters|N| |
segment|N| |

For the following connection type:
* [Salesforce](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/salesforce-connection.md)

you should use these input attributes:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
object_fields|N| |table fields
object_name|Y| |name of the table
where_clause|N| |
row_count|N| limit rows

For the following connection types:

* [Google Storage](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/gs-connection.md)
* [Hadoop Distributed File System](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/hdfs-connection.md)
* [Amazon S3](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/s3-connection.md)
* [SSH File Transfer Protoco](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)

you should use these input attributes:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
bucket|Y| |bucket or container
path|Y| |path
file_type|N|file|possible `file` or `service`
lines|N|20|lines limit
skip_header|N|false|in case of fields name in headers
record_delimiter|N|New line|possible `new_line` or `eof`
record_type|N|Delimited values|possible `delimited`, `json`, `raw`
escape|N| |escape marks
destination|N|false|
quote|N|none|for **delimited** record_type. Quotation marks, possible `none`, `\"`, `quoted_multi_line`
delimiter|N|\t|for **delimited** record_type


### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/connections/:connection_type/:connection_id/validate" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "table":"table",
    "schema_name":"schema"
  }'
```

### Response Example
```HTTP
HTTP/1.1 400 Bad Request
```

```json
{
  "error_message": "Specified project/dataset/table do not exist or missing privileges."
}
```

### Input Parameters for CURL
There is special case when **connection ID** is not required: when **type** is `curl`. In this case, `connection_id` and `connection_type` parameters can be provided to request specific connection.

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|url|Y| |url for import
|method|N|"GET"|method used for curl **GET** or **POST**
|response_type|N|"json"|possible values **raw**, **json**, **array**, **line_delimited_json**
|lines|N|20|
|username|N| |
|password|N| |
|connection_type|N| Valid [connection type](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/sections/list-connection-types.md) |
|connection_id|N| |
|headers|N| |headers syntax: {"header_name1": "header_value1", "header_name2": "header_value2"}
|body|N| |

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/connections/curl/validate" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "url":"https://api.github.com/users/user/path",
    "usaername":"uname",
    "password":"pwd1"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
  true
```
