## Update Account

### Description
This call updates account.

The details returned for the updated account are:

* **id** - the account's string identifier
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
* **role** - the member's role in the account ("admin" or "member")
* **owner** - indicator if the member is the account owner
* **members_count** - the number of members in the account
* **packages_count** - the number of packages for the account
* **jobs_count** - the number of jobs for the account
* **running_jobs_count** - the number of running jobs for the account

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
account_id|Y| |The account string identifier. Account ID provided in URL identifies account but account_id parameter passed in JSON allows to change ID.
name|N| |The account's name.
location|N| |The account's location.
region|N| |The account's region.
billing_email|N| |The account's billing email
gravatar_email|N| |The account's gravatar email

### Request (Curl Call) Syntax
```shell
curl -X PUT -H "Content-Type: application/json" -H "Accept: application/vnd.xplenty+json, version=2" \
    -u <APIkey>: "https://api.xplenty.com/accounts/<accountID>" \
    -d '{
      "account_id": "<accountID>",
      "name": "<name>",
      "location": "<location>",
      "region": "<region>",
      "billing_email": "<billingEmail>",
      "gravatar_email": "<gravatarEmail>"
    }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":"sample-admin",
  "name":"Sample Admin",
  "region":"amazon-web-services::us-east-1",
  "location":null,
  "billing_email":"admin@example.com",
  "gravatar_email":"admin@example.com",
  "avatar_url":"http://gravatar.com/avatar/d24d8cd923f00b204e9800998ecf8427e.png?d=retro&s=140",
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z",
  "schedules_count":0,
  "connections_count":2,
  "role":"member",
  "owner":false,
  "members_count":3,
  "packages_count":0,
  "jobs_count":1,
  "running_jobs_count":0
}
```
