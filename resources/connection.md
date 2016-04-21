An Xplenty **connection** contain access information required to connect to your various data stores.
The access information is stored securely and can only be used by your account's members.

Xplenty provides tha following types of connections:
* **Database**:
  * [Postgres](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/postgres.md)
* **Cloud Storage**:
  * [Google Storage](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connections/gs.md)
  *

  CLOUD:
  's3' - no properties
  'swift' -     :region, :authentication_service, :private_authentication_service, :auth_method, :tenant_id, :tenant_name
  'rackspace' - :region, :authentication_service, :private_authentication_service, :auth_method, :tenant_id, :tenant_name + auth_type
  'softlayer' - :region, :authentication_service, :private_authentication_service, :auth_method, :tenant_id, :tenant_name
  'sftp' -  host, :port, :auth_method
  'gs' - :product_id
  'hdfs' - :name_node_host, :name_node_port, :httpfs_host, :httpfs_port
  'adwords' -   :refresh_token, :refresh_token, :uid, :expires, :expires_at
  'bingads' -   :refresh_token, :refresh_token, :uid, :expires, :expires_at
  'analytics' - :refresh_token, :refresh_token, :uid, :expires, :expires_at
  'salesforce'- :refresh_token, :refresh_token, :uid, :expires, :expires_at + :instance_url, :environment



  DB:
  - segment - :ssl, :schema, :region
  - redfish - :ssl, :schema, :region
  - herokua - :ssl, :schema
  - sqlserver - :schema
  - mongo -   :ssl, :read_preference, :authentication_database
  - bigquery - :region
  - postgres - :ssl, :schema
  - googlecloudsql - no properties
  - hana - no properties
  - mysql - no properties
  - redis - no properties

### Connection Attributes

* **id** - the connection's numeric identifier
* **name** - the descriptive name given to the connection
* **unique_id** - the unique connection's identifier
* **created_at** - the date and time the connection was created
* **updated_at** - the date and time the connection was last updated
* **type** - the type of the connection. Possible values are:
  * **Database** - types for database connection:
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
    TYPE_REDIS = 'redis'


  * **Cloud Storage** - types for cloud storage connection:
    * **s3** - Amazon S3
    * **swift** - Swift (OpenStack Object Storage)
    * **gs** - Google Cloud Storage
    * **rackspace** - Rackspace Cloud Files
    * **softlayer** - SoftLayer Object Storage
    * **hdfs** - Hadoop Distributed File System
    * **adwords** - Google AdWords
    TYPE_GOOGLE_ANALYTICS => GoogleAnalyticsConnection.model_name,
    TYPE_BING_ADS => BingAdsConnection.model_name,
    TYPE_SFTP => SftpConnection.model_name,
    TYPE_SALESFORCE => SalesforceConnection.model_name

* **url** - the connection resource URL
