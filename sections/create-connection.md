## Create Account Connection

### Description
Create a new Connection. Xplenty provides tha following types of connections:

* [Bigquery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bigquery-connection.md)
* [Google Cloud SQL Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/googlecloud.md)
* [Heroku](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/heroku-connection.md)
* [MongoDB](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mongo-connection.md)
* [MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mysql-connection.md)
* [PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/postgres-connection.md)
* [Redshift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redshift-connection.md)
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
* [SSH File Transfer Protocol (SFTP)](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)
* [Softlayer](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/softlayer-connection.md)
* [Swift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/swift-connection.md)

### Input Parameters
The **connection type** and **connection ID** must be supplied at the end of the request URL.

Every connection has input attributes specific for it's type.

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/connections/:type" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Amazon S3 sample connection",
    "host": "sample_host_name"
    "username": "xplentyxplentyxplent",
    "password": "xplenty-passwordxplexplenty-passwordxple"
  }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```

```json
{
  "id":53,
  "name":"Amazon S3 sample connection",
  "username": "xplentyxplentyxplent",
  "unique_id":"S3_CONNECTION_53",
  "created_at":"2016-04-21T13:55:43Z",
  "updated_at":"2016-04-21T13:55:43Z",
  "type":"s3",
  "url":"https://api.xplenty.com/test-account/api/connections/s3/53
}

```
