## Provides help articles and videos links

### Connections
Xplenty provides tha following types of connections:

* [BigQuery](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bigquery-connection.md)
* [Google Cloud SQL Database](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/googlecloud.md)
* [Heroku](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/heroku-connection.md)
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
* [Salesforce](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/salfesforce-connection.md)
* [SSH File Transfer Protocol (SFTP)](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/sftp-connection.md)
* [Softlayer](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/softlayer-connection.md)
* [Swift](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/swift-connection.md)

### Input Parameters
The **connection type** must be supplied. Possible to specify **help_action** scope as `edit`, `index` or `new`.
Additional `setup_omniauthable` for omniauthable connections:

* [Google AdWords](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/adwords-connection.md)
* [Google Analytics](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/analytics-connection.md)
* [Bing Ads](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bingads-connection.md)
* [Salesforce](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/salfesforce-connection.md)

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/:connection_type/help"
```

### Response Example
```HTTP
HTTP/1.1 200 Created
```

```json
{
  "edit": [
    {
      "title": "Allow Xplenty access to your MongoDB",
      "type": "article",
      "url": "http://community.xplenty.com/knowledgebase/articles/429203"
    }
  ],
  "index": [
    {
      "title": "Defining connections",
      "type": "article",
      "url": "http://community.xplenty.com/knowledgebase/articles/180952"
    }
  ],
  "new": [
    {
      "title": "Allow Xplenty access to your MongoDB",
      "type": "article",
      "url": "http://community.xplenty.com/knowledgebase/articles/429203"
    }
  ]
}
```

### Other actions requiring account id

|path|help_action attributes|
|----|---------|
|/:account_id/api/connections/help|index, new
|/:account_id/api/packages/help|edit,index
|/:account_id/api/clusters/help|index,show
|/:account_id/api/schedules/help|edit, index, new, show
|/:account_id/api/members/help|index
|/:account_id/api/home/help|dashboard
|/:account_id/api/plans/help|edit
|/:account_id/api/accounts/help|edit
|/:account_id/api/hooks/help|index, new_index, slack, pagerduty, hipchat, email, web

### Other actions without account id
|path|help_action attributes|
|----|---------|
/user/notifications/help|show
/user/help|edit, edit_password
/user/keys/help|index, new
/user/console/help|-


