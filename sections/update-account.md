## Update Account

### Description
This call updates [account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/account.md).

Note: Changing the specified account's string identifier is possible by including a new identifier in the payload as `account_id`.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
account_id|Y| |The account string identifier.
name|N| |The account's name.
location|N| |The account's location.
region|N| |The account's region.
billing_email|N| |The account's billing email
gravatar_email|N| |The account's gravatar email

### Request (Curl Call) Syntax
```shell
$ curl -X PUT -u api_key: "https://api.xplenty.com/accounts/:account_id" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Sample Admin",
    "location": "California",
    "region": "amazon-web-services::us-east-1",
    "billing_email": "billing@example.com",
    "gravatar_email": "gravater@example.com"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":"1",
  "name":"Sample Admin",
  "uname": "u_1",
  "account_id":"sample-admin"
  "region":"amazon-web-services::us-east-1",
  "location":"California",
  "billing_email":"billing@example.com",
  "gravatar_email":"gravater@example.com",
  "avatar_url":"http://gravatar.com/avatar/d24d8cd923f00b204e9800998ecf8427e.png?d=retro&s=140",
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z",
  "schedules_count":0,
  "connections_count":2,
  "role":"member",
  "permissions":["viewAccountInfo", "viewAccountUsage", "listMembers", "deleteMember", "viewAccountMember", "listHooks", "viewHook", "createHook", "updateHook", "deleteHook", "listConnections", "viewConnection", "createConnection", "testConnection", "importConnection", "updateConnection", "deleteConnection", "listPackages", "viewPackage", "createPackage", "updatePackage", "deletePackage", "validatePackage", "listPackageTemplates", "listJobs", "viewJob", "createJob", "listClusters", "viewCluster", "createCluster", "updateCluster", "deleteCluster", "listSchedules", "viewSchedule", "createSchedule", "updateSchedule", "deleteSchedule"],
  "owner_id":1,
  "members_count":3,
  "packages_count":0,
  "jobs_count":1,
  "running_jobs_count":0,
  "hooks_count":0,
  "url":"https://api.xplenty.com/accounts/sample-admin",
  "public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCoBCkf9FTqAktQlAVLPAC7eMftuaAcxKtPwPPK/mwEAF0Xx7s0AgbsYws8MTsZyMic3aQxDMDn0gZYPOO6ws9+Fk51dBXCWVTgJMB7a01RdmHOV6nX4VNKnc5NRfB8bM8hvWm1UoeIUW6EAsFFiXlwnkLHcodjTjt/LxCXGZftjw== admin@example.com"
}
```
