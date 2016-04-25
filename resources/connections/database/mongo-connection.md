### Mongo Database Connection Attributes

* **id** - the connection's numeric identifier
* **type** - `mongo`
* **name** - the descriptive name given to the connection
* **username** - the database user name
* **password** - the database user password
* **unique_id** - the unique connection's identifier
* **created_at** - the date and time the connection was created
* **updated_at** - the date and time the connection was last updated
* **url** - the connection resource URL
* **database** - the name of database to use
* **host** - the name of the host to connect to
* **port** - the TCP Port to connect to. The default is 27017
* **direct** - determines if connection is direct
* **tunnel_type** - defines type of the tunnel
* **properties** - Individual connection properties:
  * **ssl** - determines whether to connect to the database using SSL
  * **read_preference** - determines how the connection should route read operations to members of a replica set
  * **authentication_database** - the name of the database to use for authentication. Leave empty to use default database
