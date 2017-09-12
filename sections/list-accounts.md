## List User's Accounts 

### Description
List active [accounts](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/account.md) in which the authenticated user is a member of (with either admin or member role). Optionally, you can supply the input parameters to filter the account list so that it contains only accounts with a specific role or id, and to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
role|N|"all"|Possible values: ```admin```, ```member```, ```all```. The call will return only accounts where the authenticated user has the given role, or all the accounts if the value is not specified or the 'all' value is specified.
sort|N|"created"|Possible values are  ```updated```, ```created```, ```id```, ```name```.
direction|N|"desc"|Possible values are: ```asc```, ```desc```. The accounts will be sorted in ascending or descending order of the "sort" attribute.
since|N| |The account list will only contain accounts updated at the given time or later. The time must be formatted as UTC in the ISO 8601 format: ```YYYY-MM-DDTHH:MM:SSZ```. Example: “2013-01-17T22:41:21Z”.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/accounts" \
  -H "Accept: application/vnd.xplenty+json, version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id":1,
    "account_id":"sample-account-1",
    "name":"Xplenty Admin",
    "uname": "u_1",
    "region":"amazon-web-services::us-east-1",
    "location":null,
    "billing_email":"billing@example.com",
    "gravatar_email":"gravatar@example.com",
    "avatar_url":"http://gravatar.com/avatar/d41d8cd98f00b204e9800998ecf8427e.png?d=retro&s=140",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z",
    "schedules_count":0,
    "connections_count":2,
    "role":"admin",
    "permissions":["viewAccountInfo", "updateAccountInfo", "changeAccountOwner", "deleteAccount", "viewAccountBillingInfo", "updateAccountBillingInfo", "viewAccountUsage", "listMembers", "inviteMember", "deleteMember", "updateMemberRole", "viewAccountMember", "listHooks", "viewHook", "createHook", "updateHook", "deleteHook", "listConnections", "viewConnection", "createConnection", "testConnection", "importConnection", "updateConnection", "deleteConnection", "listPackages", "viewPackage", "createPackage", "updatePackage", "deletePackage", "validatePackage", "listPackageTemplates", "listJobs", "viewJob", "createJob", "listClusters", "viewCluster", "createCluster", "updateCluster", "deleteCluster", "listSchedules", "viewSchedule", "createSchedule", "updateSchedule", "deleteSchedule"], 
    "is_owner":true,
    "owner_id":1,
    "members_count":2,
    "packages_count":51,
    "jobs_count":0,
    "running_jobs_count":0,
    "hooks_count":0,
    "url":"https://api.xplenty.com/accounts/sample-account-1",
    "public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCoBCkf9FTqAktQlAVLPAC7eMftuaAcxKtPwPPK/mwEAF0Xx7s0AgbsYws8MTsZyMic3aQxDMDn0gZYPOO6ws9+Fk51dBXCWVTgJMB7a01RdmHOV6nX4VNKnc5NRfB8bM8hvWm1UoeIUW6EAsFFiXlwnkLHcodjTjt/LxCXGZftjw== xplenty@example.com",
    "tunnel_host": "tunnel.xplenty.com"
  },
  {
    "id":2,
    "account_id":"sample-account-2",
    "name":"Sample Admin",
    "uname": "u_2",
    "region":"amazon-web-services::us-east-1",
    "location":null,
    "billing_email":"billing@example.com",
    "gravatar_email":"gravatar@example.com",
    "avatar_url":"http://gravatar.com/avatar/d24d8cd923f00b204e9800998ecf8427e.png?d=retro&s=140",
    "created_at":"2015-02-04T12:51:04Z",
    "updated_at":"2015-02-04T12:51:04Z",
    "schedules_count":0,
    "connections_count":2,
    "role":"member",
    "permissions":["viewAccountInfo", "viewAccountUsage", "listMembers", "deleteMember", "viewAccountMember", "listHooks", "viewHook", "createHook", "updateHook", "deleteHook", "listConnections", "viewConnection", "createConnection", "testConnection", "importConnection", "updateConnection", "deleteConnection", "listPackages", "viewPackage", "createPackage", "updatePackage", "deletePackage", "validatePackage", "listPackageTemplates", "listJobs", "viewJob", "createJob", "listClusters", "viewCluster", "createCluster", "updateCluster", "deleteCluster", "listSchedules", "viewSchedule", "createSchedule", "updateSchedule", "deleteSchedule"],
    "owner_id":1,
    "members_count":3,
    "packages_count":35,
    "jobs_count":1,
    "running_jobs_count":0,
    "hooks_count":0,
    "url":"https://api.xplenty.com/accounts/sample-account-2",
    "public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCoBCkf9FTqBktQlAVLPAC7eMftuaAcxKtPwPPK/mwEAF0Xx7s0AgbsYws8MTsZyMic3aQxDMDn0gZYPOO6ws9+Fk51dBXCWVTgJMB7a01RdmHOV6nX4VNKnc5NRfB8bM8hvWm1UoeIUW6EAsFFiXlwnkLHcodjTjt/LxCXGZftjw== xplenty2@example.com",
    "tunnel_host": "tunnel.xplenty.com"
  }
]
```
