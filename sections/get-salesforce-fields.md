## Get Salesforce fields

### Description
Information about fields of given **object**.

### Input Parameters
Required parameter is the **connection_id** and **object_name**.
Possible to add **force_fetch** which determines if clear cache or not.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/metadata/salesforce/:connection_id/fields" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{"object_name": "Account"}'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "fields": [
    {
      "name": "ShippingLatitude",
      "length": 0,
      "type": "double"
    },
    {
      "name": "LastModifiedDate",
      "length": 0,
      "type": "datetime"
    },
    {
      "name": "Description",
      "length": 32000,
      "type": "string"
    },
    {
      "name": "BillingCity",
      "length": 40,
      "type": "string"
    },
    {
      "name": "JigsawCompanyId",
      "length": 20,
      "type": "string"
    },
    {
      "name": "Website",
      "length": 255,
      "type": "string"
    },
    {
      "name": "LastReferencedDate",
      "length": 0,
      "type": "datetime"
    },
    {
      "name": "Account_Status__c",
      "length": 255,
      "type": "string"
    },
    {
      "name": "BillingLatitude",
      "length": 0,
      "type": "double"
    },
    {
      "name": "NumberOfEmployees",
      "length": 0,
      "type": "int"
    },
    {
      "name": "Name",
      "length": 255,
      "type": "string"
    },
    {
      "name": "Industry",
      "length": 40,
      "type": "string"
    },
    {
      "name": "OwnerId",
      "length": 18,
      "type": "string"
    },
    {
      "name": "CreatedById",
      "length": 18,
      "type": "string"
    },
    {
      "name": "BillingLongitude",
      "length": 0,
      "type": "double"
    },
    {
      "name": "Phone",
      "length": 40,
      "type": "string"
    },
    {
      "name": "BillingGeocodeAccuracy",
      "length": 40,
      "type": "string"
    },
    {
      "name": "ShippingCountry",
      "length": 80,
      "type": "string"
    },
    {
      "name": "BillingPostalCode",
      "length": 20,
      "type": "string"
    },
    {
      "name": "ShippingCity",
      "length": 40,
      "type": "string"
    },
    {
      "name": "PhotoUrl",
      "length": 255,
      "type": "string"
    },
    {
      "name": "MasterRecordId",
      "length": 18,
      "type": "string"
    },
    {
      "name": "Xplenty_Account_ID__c",
      "length": 0,
      "type": "double"
    },
    {
      "name": "ParentId",
      "length": 18,
      "type": "string"
    },
    {
      "name": "IsDeleted",
      "length": 0,
      "type": "boolean"
    },
    {
      "name": "LastViewedDate",
      "length": 0,
      "type": "datetime"
    },
    {
      "name": "ShippingGeocodeAccuracy",
      "length": 40,
      "type": "string"
    },
    {
      "name": "ShippingStreet",
      "length": 255,
      "type": "string"
    },
    {
      "name": "SystemModstamp",
      "length": 0,
      "type": "datetime"
    },
    {
      "name": "Trial_Status__c",
      "length": 0,
      "type": "boolean"
    },
    {
      "name": "Type",
      "length": 40,
      "type": "string"
    },
    {
      "name": "BillingCountry",
      "length": 80,
      "type": "string"
    },
    {
      "name": "BillingStreet",
      "length": 255,
      "type": "string"
    },
    {
      "name": "ShippingPostalCode",
      "length": 20,
      "type": "string"
    },
    {
      "name": "CreatedDate",
      "length": 0,
      "type": "datetime"
    },
    {
      "name": "LastActivityDate",
      "length": 0,
      "type": "datetime"
    },
    {
      "name": "ShippingState",
      "length": 80,
      "type": "string"
    },
    {
      "name": "Id",
      "length": 18,
      "type": "string"
    },
    {
      "name": "Fax",
      "length": 40,
      "type": "string"
    },
    {
      "name": "LastModifiedById",
      "length": 18,
      "type": "string"
    },
    {
      "name": "BillingState",
      "length": 80,
      "type": "string"
    },
    {
      "name": "ShippingLongitude",
      "length": 0,
      "type": "double"
    },
    {
      "name": "AnnualRevenue",
      "length": 0,
      "type": "double"
    }
  ]
}
```
