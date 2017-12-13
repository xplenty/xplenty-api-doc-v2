## Provides help articles and videos links

### Connections
Xplenty provides the following types of connections:

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
* [Azure Blob Storage](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/azure-blob-storage-connection.md)

### Input Parameters
The **connection type** must be supplied. Possible to specify **help_action** scope as `edit`, `index` or `new`.
Additional `setup_omniauthable` for omniauthable connections:

* [Google AdWords](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/adwords-connection.md)
* [Google Analytics](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/analytics-connection.md)
* [Bing Ads](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/bingads-connection.md)
* [Salesforce](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/salesforce-connection.md)
* [Intercom](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/intercom-connection.md)
* [Facebook Ads Insights](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/facebook-ads-insights-connection.md)
* [Xero](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/xero-connection.md)

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


