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
$ curl -X PUT -u api_key: "https://api.xplenty.com/accounts/:account_id" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "account_id": "sample-admin",
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
  "owner_id":1,
  "members_count":3,
  "packages_count":0,
  "jobs_count":1,
  "running_jobs_count":0,
  "hooks_count":0,
  "completed_data_processes_count":0,
  "idle_data_processes_count":0,
  "pending_data_processes_count":0,
  "stopped_data_processes_count":0,
  "failed_data_processes_count":0,
  "pending_stoppage_data_processes_count":0,
  "stopping_data_processes_count":0,
  "idle_clusters_count":0,
  "pending_clusters_count":0,
  "pending_terminate_clusters_count":0,
  "error_clusters_count":0,
  "creating_clusters_count":0,
  "available_clusters_count":0,
  "scaling_clusters_count":0,
  "terminating_clusters_count":0,
  "idle_addons_count":0,
  "error_addons_count":0,
  "pending_provision_addons_count":0,
  "provisioning_addons_count":0,
  "available_addons_count":0,
  "pending_scale_addons_count":0,
  "scaling_addons_count":0,
  "pending_deprovision_addons_count":0,
  "deprovisioning_addons_count":0,
  "addon_services_count":0,
  "pending_approval_addon_services_count":0,
  "approved_addon_services_count":0,
  "public_addon_services_count":0,
  "disapproved_addon_services_count":0,
  "active_jobs_count":0,
  "job_validations_count":0,
  "running_job_validations_count":0,
  "completed_job_validations_count":0,
  "failed_job_validations_count":0,
  "enabled_schedules_count":0,
  "disabled_schedules_count":0,
  "url":"https://api.xplenty.com/accounts/sample-admin",
  "public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCoBCkf9FTqAktQlAVLPAC7eMftuaAcxKtPwPPK/mwEAF0Xx7s0AgbsYws8MTsZyMic3aQxDMDn0gZYPOO6ws9+Fk51dBXCWVTgJMB7a01RdmHOV6nX4VNKnc5NRfB8bM8hvWm1UoeIUW6EAsFFiXlwnkLHcodjTjt/LxCXGZftjw== admin@example.com"
}
```
