## Search Schedules

### Description
Search engine was optimized to find the best match using intuitive syntax. Results are ordered by relevance by default, so you can easily compare all returned records and choose the best one.
Format of the query string is the following:
`attribute1:value1 attribute2:"some terms with spaces" date_attribute1:>2016-01-01 date_attribute2:<2016-01-02 -attribute2:value3 other text`
Here are a few important rules:

1. For comparable attributes like integer or date, you can use the following operators:
  * `:` - equal
  * `:>` - greater than or equal
  * `:<` - less than or equal
2. Negation is represented by `-` sign at the beginning of the attribute like: `-name:John`. It means we do not want to have results where value of the `name` attribute contains `John` phrase.
3. Negation cannot be used for comparable types like integer or date.
3. When an attribute with the same sign is used twice in a search query - the two instances are joined with OR, in case of different sign, phrases are joined with AND.
4. Two different attributes are joined with AND.

Possible attributes:

* **id**
* **name**
* **description**
* **status**
* **package** - search in related packages by the **name** attribute

Free text (not assigned to any attribute) will search in name and description. They will be joined with OR.

Please read the document describing [schedule](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/schedule.md) for other details.


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
q|Y| |Terms, e.g. `name:"schedule 1" test schedule`
sort|N|"relevance"|Possible values are `modified`, `created` or `relevance`. The schedule list will be sorted by the schedules' `updated_at`, `created_at` attributes or relevance of the search results.
direction|N|"desc"|Possible values are: `asc`, `desc`. The schedules will be sorted in ascending or descending order of the `sort` attribute.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/schedules/search" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "q":"name:\"schedule 1\" test schedule",
    "sort":"created",
    "direction":"desc"
  }'
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "created_at": "2014-09-25T08:48:51Z",
    "name": "My Schedule",
    "description": "A daily schedule",
    "execution_count": 0,
    "id": 2,
    "interval_amount": 1,
    "interval_unit": "days",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
    "overlap":true,
    "reuse_cluster_strategy":"any",
    "task": {
      "nodes": 3,
      "packages": [
        {
          "package_id": "1",
          "variables": {
            "MY_VAR": "'My Var Value'"
          }
        }
      ],
      "terminate_on_idle": true,
      "time_to_idle": 60
    },
    "updated_at": "2014-10-29T14:22:05Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/2",
    "html_url": "https://xplenty.com/xplenation/schedules/2"
  },
  {
    "created_at": "2014-09-25T08:48:51Z",
    "name": "My Schedule",
    "description": "A monthly schedule",
    "execution_count": 0,
    "id": 2,
    "interval_amount": 1,
    "interval_unit": "months",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
    "overlap":false,
    "reuse_cluster_strategy":"none",
    "task": {
      "nodes": 3,
      "packages": [
        {
          "package_id": "1",
          "variables": {
            "MY_VAR": "'My Var Value'"
          }
        }
      ],
      "terminate_on_idle": true,
      "time_to_idle": 60
    },
    "updated_at": "2014-10-29T14:22:05Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/2",
    "html_url": "https://xplenty.com/xplenation/schedules/2"
  },
  {
    "created_at": "2014-09-25T08:48:51Z",
    "name": "My Schedule",
    "description": "An hourly schedule (every 2 hours)",
    "execution_count": 0,
    "id": 2,
    "interval_amount": 2,
    "interval_unit": "hours",
    "last_run_at": null,
    "last_run_status": null,
    "next_run_at": "2014-09-25T08:48:00Z",
    "owner_id": 1,
    "start_at": "2014-09-25T08:48:00Z",
    "status": "enabled",
    "overlap":true,
    "reuse_cluster_strategy":"self",
    "task": {
      "nodes": 3,
      "packages": [
        {
          "package_id": "1",
          "variables": {
            "MY_VAR": "'My Var Value'"
          }
        }
      ],
      "terminate_on_idle": true,
      "time_to_idle": 60
    },
    "updated_at": "2014-10-29T14:22:05Z",
    "url": "https://api.xplenty.com/xplenation/api/schedules/2",
    "html_url": "https://xplenty.com/xplenation/schedules/2"
  }
]
```
