## Test Connection

### Description
Checks if it is possible to establish connection. Xplenty provides tha following types of connections:

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

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "/:account_id/api/connections/:connection_type/:connection_id/test" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|url|Y| |url for test
|method|Y|"GET"|**GET** or **POST**
|response_type|N|"json"|possible values **raw**, **json**, **array**, **line_delimited_json**
|lines|N|20|
|username|N| |
|password|N| |
|headers|N| |
|body|N| |

```shell
$ curl -X POST -u api_key: "/:account_id/api/connections/curl/test" \
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
