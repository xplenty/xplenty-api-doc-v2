### Swift (OpenStack Object Storage) Connection Attributes

* **id** - the connection's numeric identifier
* **type** - `swift`
* **name** - the descriptive name given to the connection
* **username** - the username you use to access the Swift service. If required by your provider, you might also have to enter the account in the following format: `account:username`. This format is not required when using a Tenant Name (see below).
* **password** - the password assigned to your Swift account
* **unique_id** - the unique connection's identifier
* **created_at** - the date and time the connection was created
* **updated_at** - the date and time the connection was last updated
* **tenant_name** - a container used to group or isolate resources and/or identity objects, as defined by your Swift service provider. It is optional attribute.
* **auth_method** - the authorization system used by the identity service. Possible values: **swauth**, **keystone**
* **authentication_service** - the url of the authentication service used to authenticate you
* **private_authentication_service** - name of the private authetication service
* **url** - the connection resource URL (API)
