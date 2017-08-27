## Create Account

### Description
Creates a new [account](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/account.md). This operation is possible only by confirmed users.

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|name|Y| |The name of the account.
|account_id|N| |Unique identifier of the account.
|region|Y| |The default region for the account.


### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/accounts" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name" : "Sample account",
    "account_id" : "sample-account-1",
    "region" : "amazon-web-services::us-east-1"
  }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```

```json
{
  "id":1,
  "account_id":"sample-account-1",
  "name":"Sample Account",
  "uname": "u_1",
  "region":"amazon-web-services::us-east-1",
  "location":null,
  "billing_email":"",
  "gravatar_email":null,
  "avatar_url":"http://gravatar.com/avatar/.png?d=retro&s=140",
  "created_at":"2015-02-04T12:51:04Z",
  "updated_at":"2015-02-04T12:51:04Z",
  "schedules_count":0,
  "connections_count":0,
  "role":"admin",
  "permissions":["viewAccountInfo", "updateAccountInfo", "changeAccountOwner", "deleteAccount", "viewAccountBillingInfo", "updateAccountBillingInfo", "viewAccountUsage", "listMembers", "inviteMember", "deleteMember", "updateMemberRole", "viewAccountMember", "listHooks", "viewHook", "createHook", "updateHook", "deleteHook", "listConnections", "viewConnection", "createConnection", "testConnection", "importConnection", "updateConnection", "deleteConnection", "listPackages", "viewPackage", "createPackage", "updatePackage", "deletePackage", "validatePackage", "listPackageTemplates", "listJobs", "viewJob", "createJob", "listClusters", "viewCluster", "createCluster", "updateCluster", "deleteCluster", "listSchedules", "viewSchedule", "createSchedule", "updateSchedule", "deleteSchedule"], 
  "owner_id":1,
  "is_owner":true,
  "members_count":1,
  "packages_count":0,
  "jobs_count":0,
  "deliveries_count":0,
  "running_jobs_count":0,
  "hooks_count":0,
  "url":"https://api.xplenty.com/accounts/sample-account-1",
  "public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCoBCkf9FTqAktQlAVLPAC7eMftuaAcxKtPwPPK/mwEAF0Xx7s0AgbsYws8MTsZyMic3aQxDMDn0gZYPOO6ws9+Fk51dBXCWVTgJMB7a01RdmHOV6nX4VNKnc5NRfB8bM8hvWm1UoeIUW6EAsFFiXlwnkLHcodjTjt/LxCXGZftjw== xplenty@example.com",
  "tunnel_host": "tunnel.xplenty.com"  
}
```
