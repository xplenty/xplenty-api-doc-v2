### Sftp Connection Attributes

* **id** - the connection's numeric identifier
* **type** - `swift`
* **name** - the descriptive name given to the connection
* **username** - the SFTP server user name
* **password** - the SFTP server password. Only required for Password Authentication method
* **unique_id** - the unique connection's identifier
* **created_at** - the date and time the connection was created
* **updated_at** - the date and time the connection was last updated
* **properties** - Individual connection properties:
  * **host** - the name of the SFTP server to connect to
  * **port** - the TCP Port to connect to. Default is 22
  * **auth_method** - the authentication method to use. Possible values: **password**, **key**
