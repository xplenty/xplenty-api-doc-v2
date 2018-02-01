## Test Connection

### Description
Checks if it is possible to establish connection. Xplenty provides the following types of connections:

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
* [Xero](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/xero-connection.md)
* [Snowflake](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/snowflake-connection.md)
* [Azure Blob Storage](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/azure-blob-storage-connection.md)

### Input Parameters for above connections
The **connection ID** and **connection type**. Possible values of the type are listed above (on the connection types' pages).

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/connections/:connection_type/:connection_id/test" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
  true
```

### Input Parameters for CURL
There is special case when **connection ID** is not required: when **type** is `curl`. In this case, `connection_id` and `connection_type` parameters can be provided to request specific connection.


|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|url|Y| |url for test
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
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/connections/curl/test" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 400 Bad Request
```

```json
{
  "error_message": "Could not make CURL request, please verify connection settings and security/firewall options"
}
```
