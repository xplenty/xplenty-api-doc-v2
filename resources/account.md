An Xplenty **account** represents a related group (usually a company) of Xplenty **users**.

### Account Attributes

* **id** - the account's numeric identifier
* **account_id** - the account's unique identifier
* **uname** - the account's numeric identifier with `u_` prefix
* **name** - the name given to the account upon creation
* **region** - the account's region
* **location** - the account's location
* **billing_email** - the account's billing email
* **gravatar_email** - the account's gravatar email
* **avatar_url** - the url for the account's avatar
* **created_at** - the date and time the account was created
* **updated_at** - the date and time the account was last updated
* **schedules_count** - the number of schedules for the account
* **connections_count** - the number of connections for the account
* **role** - the authenticated users' role in the account
* **permissions** - the permissions the authenticated user has on the account
* **owner_id** - the numeric identifier of the account's owner
* **is_owner** - indicator if the authenticated user is the owner of the account
* **members_count** - the number of members in the account
* **packages_count** - the number of packages for the account
* **jobs_count** - the number of jobs for the account
* **running_jobs_count** - the number of running jobs for the account
* **hooks_count** - the number of service hooks for the account
* **url** - the account resource URL
* **public_key** - the account ssh public key generated upon creation
