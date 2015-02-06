## List Account Connections

### Description
This call returns list of account connections.

Optionally, you can supply the input parameters to filter the connection list so that it contains
specific types only and to determine the order by which the list will be sorted.
Possible input values for type parameter:

* s3
* swift
* gs
* rackspace
* softlayer
* hdfs
* adwords
* analytics
* postgres
* redshift
* mongo
* redis
* mysql
* hana
* oracle
* sqlserver
* herokupostgres
* googlecloudsql
* bigquery
* segment


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
type|N| |Possible values are listed above. The call will return only connections with the given types, or all the connections if value is not specified. Values can be joined with commas, e.g. 's3,postgres,redis'.
sort|N|"created"|Possible values are ```id```, ```name```, ```type```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The connection will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The connection list will only contain connections created at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/connections?type=<typeFilter>&sort=<sortField>&direction=<sortDirection>&since=<sinceTime>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[{
    "id": 323,
    "name": "App Logs (MongoDB)",
    "type": "mongo"
}, {
    "id": 324,
    "name": "Website Logs (MongoDB)",
    "type": "mongo"
}, {
    "id": 325,
    "name": "Website Logs (S3)",
    "type": "s3"
}, {
    "id": 326,
    "name": "My Google Adwords",
    "type": "adwords"
}, {
    "id": 318,
    "name": "Data Warehouse (Redshift)",
    "type": "redshift"
}]
```
