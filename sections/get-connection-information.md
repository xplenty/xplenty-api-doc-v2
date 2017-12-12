## Get Account Connection Information

### Description
Information about an existing connection. Xplenty provides the following types of connections:

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
* [SSH File Transfer Protocol (SFTP)](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)
* [NetSuite](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/net-suite-connection.md)
* [Google Cloud Spanner](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-spanner-connection.md)
* [Oracle Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/oracle-connection.md)
* [Intercom](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/intercom-connection.md)
* [Facebook Ads Insights](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/facebook-ads-insights-connection.md)
* [Xero](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/xero-connection.md)

### Input Parameters
The **connection type** and **connection ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/:type/:id" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":53,
  "name":"Amazon S3 sample connection",
  "username": "johndoe",
  "unique_id":"S3_CONNECTION_53",
  "created_at":"2016-04-21T13:55:43Z",
  "updated_at":"2016-04-21T13:55:43Z",
  "type":"s3",
  "url":"https://api.xplenty.com/xplenation/api/connections/s3/53
}
```
