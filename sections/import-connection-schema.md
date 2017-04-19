## Import Connection Schema.

### Description
Imports schema of the connection. Xplenty provides the following types of connections:

* [BigQuery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bigquery-connection.md)
* [Google Cloud SQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-sql-connection.md)
* [Heroku Postgres](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/heroku-postgres-connection.md)
* [MongoDB](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mongo-connection.md)
* [MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mysql-connection.md)
* [PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/postgres-connection.md)
* [Redshift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redshift-connection.md)
* [Segment](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/segment-connection.md)
* [SQL Server](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sqlserver-connection.md)
* [Bing Ads](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bingads-connection.md)
* [Google Storage](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/gs-connection.md)
* [Google AdWords](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/adwords-connection.md)
* [Google Analytics](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/analytics-connection.md)
* [Hadoop Distributed File System](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/hdfs-connection.md)
* [Rackspace](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/rackspace-connection.md)
* [Amazon S3](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/s3-connection.md)
* [Salesforce](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/salesforce-connection.md)
* [SSH File Transfer Protoco](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)
* [Softlayer](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/softlayer-connection.md)
* [Swift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/swift-connection.md)
* [NetSuite](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/net-suite-connection.md)
* [Google Cloud Spanner](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-spanner-connection.md)
* [Oracle Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/oracle-connection.md)

### Input Parameters for connections
The **connection ID** and **connection type**. Possible values of the type are listed above (on the connection types' pages).

For the following connection types:

* [BigQuery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bigquery-connection.md)
* [Google Cloud SQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-sql-connection.md)
* [Heroku Postgres](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/heroku-postgres-connection.md)
* [MongoDB](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mongo-connection.md)
* [MySQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/mysql-connection.md)
* [PostgreSQL](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/postgres-connection.md)
* [Redshift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/redshift-connection.md)
* [Segment](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/segment-connection.md)
* [SQL Server](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sqlserver-connection.md)
* [NetSuite](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/net-suite-connection.md)
* [Google Cloud Spanner](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/google-cloud-spanner-connection.md)
* [Oracle Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/oracle-connection.md)

you should use these input attributes:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
table|Y| | name of the table
schema_name|Y| |
where_clause|N| |SQL where clause
lines|N|20|row limit

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
* [Rackspace](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/rackspace-connection.md)
* [Amazon S3](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/s3-connection.md)
* [SSH File Transfer Protoco](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)
* [Softlayer](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/softlayer-connection.md)
* [Swift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/swift-connection.md)

you should use these input attributes:

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
bucket|Y| |bucket or container
path|Y| |path
file_type|N|file|possible `file` or `service`
lines|N|20|lines limit
record_delimiter|N|New line|possible `new_line` or `eof`
record_type|N|Delimited values|possible `delimited`, `json`, `raw`
skip_header|N|false|in case of fields name in headers
escape|N| |escape marks
quote|N|none|for **delimited** record_type. Quotation marks, possible `none`, `\"`, `quoted_multi_line`
delimiter|N|\t|for **delimited** record_type

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/:connection_type/:connection_id/schema" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
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

### Input Parameters for CURL
There is special case when **connection ID** is not required: when **type** is `curl`.

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|url|Y| |url for import
|method|N|"GET"|method used for curl **GET** or **POST**
|response_type|N|"json"|possible values **raw**, **json**, **array**, **line_delimited_json**
|lines|N|20|
|username|N| |
|password|N| |
|headers|N| |headers syntax: {"header_name1": "header_value1", "header_name2": "header_value2"}
|body|N| |


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/curl/schema" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "url":"https://api.github.com/users/user/path",
    "usaername":"uname",
    "password":"pwd1",
    "response_type":"raw"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "data": [
    [
      200,
      "[{\"id\":123,\"name\":\"name\",\"full_name\":\"fullreqname/fullreqname\",\"owner\":{\"login\":\"ownerlogin\",\"id\":123,\"avatar_url\":\"https://avatars.githubusercontent.com/u/id?v=3\",\"gravatar_id\":\"\",\"url\":\"https://api.github.com/users/name\",\"html_url\":\"https://github.com/fullreqname\"}]",
      {
        "date": "Wed, 25 May 2016 10:25:41 GMT",
        "server": "GitHub.com",
        "transfer-encoding": "chunked",
        "x-ratelimit-limit": "60",
        "vary": "Accept",
        "x-frame-options": "deny",
        "x-served-by": "139317cebd6caf9cd03889139437f00b",
        "x-ratelimit-reset": "1464173473",
        "x-ratelimit-remaining": "57",
        "strict-transport-security": "max-age=31536000; includeSubdomains; preload",
        "access-control-expose-headers": "ETag, Link, X-GitHub-OTP, X-RateLimit-Limit, X-RateLimit-Remaining, X-RateLimit-Reset, X-OAuth-Scopes, X-Accepted-OAuth-Scopes, X-Poll-Interval",
        "x-github-request-id": "3656EF24:1271A:135CC22A:57457DA5",
        "access-control-allow-origin": "*",
        "x-github-media-type": "github.v3; format=json",
        "content-security-policy": "default-src 'none'",
        "x-content-type-options": "nosniff",
        "x-xss-protection": "1; mode=block",
        "content-type": "application/json; charset=utf-8",
        "etag": "W/\"a02c212fc5c56f25fcff863aaa999a6a\"",
        "cache-control": "public, max-age=60, s-maxage=60",
        "status": "200 OK"
      }
    ]
  ],
  "fields": [
    {
      "status": "int"
    },
    {
      "body": "string"
    },
    {
      "headers": "json"
    }
  ]
}
```
