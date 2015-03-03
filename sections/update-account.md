## Update Account

### Description
This call updates [account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/account.md).

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
