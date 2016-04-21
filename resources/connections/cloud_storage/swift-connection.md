### Swift (OpenStack Object Storage) Connection Attributes

* **id** - the connection's numeric identifier
* **type** - `swift`
* **name** - the descriptive name given to the connection
* **username** - the username for cloud storage
* **password** - the password used for cloud storage
* **unique_id** - the unique connection's identifier
* **created_at** - the date and time the connection was created
* **updated_at** - the date and time the connection was last updated
* **properties** - Individual connection properties:
  * **region** - name of the region
  * **tenant_id** - id of the tenant
  * **tenant_name** - name of the tenant
  * **auth_method** - authentication method (swauth || keystone)
  * **authentication_service** - name of the authetication service
  * **private_authentication_service** - name of the private authetication service
