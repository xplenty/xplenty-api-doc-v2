## Export Package as JSON

### Description
Export all the components within the package as a JSON file

### Input Parameters
The **package ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/packages/:package_id/export" \
  -H "Accept: application/vnd.xplenty+json; version=2" 
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
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
}
```
