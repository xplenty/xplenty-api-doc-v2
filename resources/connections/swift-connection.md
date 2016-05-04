### Swift (OpenStack Object Storage) Connection Attributes

|Name|Read-Only?|Required?|Default|Description|
|----|---------|---------|-------|-----------|
|id|Y| | |the connection's numeric identifier
|type|Y| | |`swift`
|name|N|Y| |the descriptive name given to the connection
|username|N|N| |the username you use to access the Swift service. If required by your provider, you might also have to enter the account in the following format: `account:username`. This format is not required when using a Tenant Name (see below).
|password|N|N| |the password assigned to your Swift account
|unique_id|Y| | |the unique connection's identifier
|created_at|Y| | |the date and time the connection was created
|updated_at|Y| | |the date and time the connection was last updated
|tenant_name|N|N| |a container used to group or isolate resources and/or identity objects, as defined by your Swift service provider. It is optional attribute
|auth_method|N|N|"swauth"|the authorization system used by the identity service. Possible values: **swauth**, **keystone**
|authentication_service|N|N| |the url of the authentication service used to authenticate you
|private_authentication_service|N|N| |name of the private authetication service
|url|Y| | |the connection resource URL (API)
