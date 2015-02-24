## Delete Account

### Description
This call deletes the given account. The operation can be executed only by the account owner.

### Notes
* Please note that this action is **irreversible**.

The details returned for the deleted account are:

* **id** - the account's numeric identifier
* **name** - the name given to the account upon creation
* **region** - the account's region
* **location** - the account's location
* **billing_email** - the account's billing email
* **gravatar_email** - the account's gravatar email
* **avatar_url** - the url for the account's avatar
* **created_at** - the date and time the account was created
* **updated_at** - the date and time the account was last updated

### Input Parameters
The **account ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/accounts/<accountID>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":"xplenty-admin",
  "name":"Xplenty Admin",
  "region":"amazon-web-services::us-east-1",
  "location":null,
  "billing_email":"admin@xplenty.com",
  "gravatar_email":"admin@xplenty.com",
  "avatar_url":"http://gravatar.com/avatar/d41d8cd98f00b204e9800998ecf8427e.png?d=retro&s=140",
  "schedules_count":0,
  "connections_count":0,
  "role":"admin",
  "owner":true,
  "members_count":1,
  "packages_count":0,
  "jobs_count":0,
  "running_jobs_count":0,
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z"
}
```
