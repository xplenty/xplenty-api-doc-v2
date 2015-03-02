## List Account Connections

### Description
This call returns list of account connections that were created by users in your account. Optionally, you can supply the input parameters to filter the connection list so that it contains only connections with
specific types and to determine the order by which the list will be sorted.

The details returned for each schedule are:

* **id** the numeric connection ID
* **name** the name given to the connection upon creation
* **type** the type of connection. Possible values are:
    * **s3** - Amazon S3
    * **swift** - Swift (OpenStack Object Storage)
    * **gs** - Google Cloud Storage
    * **rackspace** - Rackspace Cloud Files
    * **softlayer** - SoftLayer Object Storage
    * **hdfs** - Hadoop Distributed File System
    * **adwords** - Google AdWords
    * **postgres** - PostgresSQL
    * **redshift** - Amazon Redshift
    * **mongo** - MongoDB
    * **mysql** - MySQL
    * **hana** - SAP Hana
    * **sqlserver** - Microsoft SQL Server
    * **herokupostgres** - Heroku PostgresSQ
    * **googlecloudsql** - Google Cloud SQL
    * **bigquery** - Google BigQuery
    * **segment** - Segment SQL


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
type|N|"all" |Possible values are listed above or ```all```. The call will return only connections with the given types, or all the connections if the "all" value is specified. Values can be joined with commas, e.g. 's3,postgres,redis'.
sort|N|"created"|Possible values are ```id```, ```name```, ```type```, ```updated``` or ```created```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The connection will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The connection list will only contain connections updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 323,
    "name": "App Logs (MongoDB)",
    "type": "mongo",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z"
  }, 
  {
    "id": 324,
    "name": "Website Logs (MongoDB)",
    "type": "mongo",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z"
  }, 
  {
    "id": 325,
    "name": "Website Logs (S3)",
    "type": "s3",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z"
  }, 
  {
    "id": 326,
    "name": "My Google Adwords",
    "type": "adwords",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z"
  }, 
  {
    "id": 318,
    "name": "Data Warehouse (Redshift)",
    "type": "redshift",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z"
  }
]
```
