## Create Package

### Description
Create a new [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md). 
Using the output from `/export` package endpoint as an input parameter also can be used to create package.

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
source_package_id|N| |If it is provided, the new package will be a copy of package with this ID
package_template_id|N| |If it is provided, the new package will be created based on the template that is associated with this ID
name|N|"Untitled package"|Name of the package
description|N| |Description of the package
data_flow_json|N| |Data flow prepared in JSON format
variables|N| |The list of package variables in its JSON format
flow_type|N|"dataflow"|Flow type of the package. Possible values: `dataflow`, `workflow`
flow_version|N|`2.0.0`|Flow version based on our frontend version

### Request (Curl Call) Examples
#### Example 1
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/packages" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Test package 1",
    "description": "Sample description",
    "variables": {
      "variable1": "123",
      "variable2": "456"
    }
  }'
```
#### Example 2 (using an output from export API as a data input parameter)
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/packages" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "components": [
      {
        "facebook_ads_insights_source_component": {
          "id": "component-d3f86a",
          "name": "facebook_ads_insights_1",
          "alias": "facebook_ads_insights_1",
          "xy": [
            924,
            84
          ],
          "connection": {
          },
          "schema": {
            "valid": true,
            "fields": [

            ]
          },
          "with_custom_fields": false,
          "api_version": "v6.0",
          "ad_accounts": [
            "any"
          ],
          "level": "account",
          "action_report_time": "impression",
          "time_increment": "all_days",
          "filtering": "",
          "report_date_range_type": "last_7d",
          "report_date_range_min": "",
          "report_date_range_max": "",
          "manual_breakdown": "Default",
          "report_on": "all",
          "cloud_storage_connection_id": ""
        }
      },
      {
        "salesforce_source_component": {
          "id": "component-39f6fd",
          "name": "salesforce_3",
          "alias": "salesforce_3",
          "xy": [
            672,
            140
          ],
          "connection": {
          },
          "schema": {
            "valid": true,
            "fields": [

            ]
          },
          "cloud_storage_connection_id": "",
          "object_name": "",
          "where_clause": "",
          "source_action": "query",
          "access_mode": "object",
          "query": ""
        }
      },
      {
        "limit_component": {
          "id": "component-3da88f",
          "name": "limit_5",
          "alias": "limit_5",
          "xy": [
            924,
            252
          ],
          "n": 1,
          "partitioned_fields": [

          ],
          "ordered_fields": [

          ]
        }
      },
      {
        "join_component": {
          "id": "component-017e82",
          "name": "join_7",
          "alias": "join_7",
          "xy": [
            672,
            308
          ],
          "join_type": "inner",
          "optimization_type": "default",
          "relations": [

          ]
        }
      },
      {
        "union_component": {
          "id": "component-c9d8d0",
          "name": "union_8",
          "alias": "union_8",
          "xy": [
            784,
            560
          ],
          "fields": [

          ]
        }
      },
      {
        "salesforce_destination_component": {
          "id": "component-d05554",
          "name": "salesforce_9",
          "alias": "salesforce_9",
          "xy": [
            784,
            728
          ],
          "connection": {
          },
          "schema": {
            "valid": true,
            "fields": [

            ]
          },
          "cloud_storage_connection_id": "",
          "object_name": "",
          "operation_type": "insert",
          "id_field": "",
          "batch_size": 1000,
          "max_errors": 0,
          "column_mappings": [

          ],
          "database_connection_id": "undefined"
        }
      }
    ],
    "edges": [
      {
        "id": "edge-e4ff49",
        "label": "edge-e4ff49",
        "order": 0,
        "source_index": 0,
        "source": "component-d3f86a",
        "target": "component-3da88f"
      },
      {
        "id": "edge-72a9a1",
        "label": "edge-72a9a1",
        "order": 0,
        "source_index": 0,
        "source": "component-39f6fd",
        "target": "component-017e82"
      },
      {
        "id": "edge-e9b077",
        "label": "edge-e9b077",
        "order": 0,
        "source_index": 0,
        "source": "component-3da88f",
        "target": "component-c9d8d0"
      },
      {
        "id": "edge-41252b",
        "label": "edge-41252b",
        "order": 1,
        "source_index": 0,
        "source": "component-017e82",
        "target": "component-c9d8d0"
      },
      {
        "id": "edge-924b02",
        "label": "edge-924b02",
        "order": 0,
        "source_index": 0,
        "source": "component-c9d8d0",
        "target": "component-d05554"
      }
    ],
    "variables": {
    },
    "metadata": {
      "name": "New Export Json",
      "flow_type": "dataflow",
      "version": "1.2",
      "description": ""
    }
  }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```

```json
{
  "id":3,
  "name":"Test Package 1",
  "description":null,
  "variables":{},
  "flow_type":"dataflow",
  "owner_id":5,
  "created_at":"2015-02-26T11:46:05Z",
  "updated_at":"2015-02-26T11:46:05Z",
  "url":"https://api.xplenty.com/xplenation/api/packages/3",
  "html_url":"https://xplenty.com/xplenation/packages/3",
  "status":"active"
}
```
