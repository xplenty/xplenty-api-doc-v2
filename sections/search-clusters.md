## Search Clusters

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
* **nodes**
* **created**
* **terminated**

Free text (not assigned to any attribute) will search in ID and name. They will be joined with OR.

Please read the document describing [cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) for other details.


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
q|Y| |Terms, e.g. `name:"cluster 1" test cluster`
sort|N|"relevance"|Possible values are `id`, updated`, `created` or `name`. The cluster list will be sorted by the clusters' `id`, `updated_at`, `created_at` or `name` attributes or relevance if no sort parameter is specified.
direction|N|"asc"|Possible values are: `asc`, `desc`. The clusters will be sorted in ascending or descending order of the `sort` attribute.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/clusters/search" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "q":"name:\"cluster 1\" test cluster",
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
    "id": 99,
    "name": "Daily Outliers Test #100",
    "description": "Daily Outliers Test",
    "status": "terminated",
    "owner_id": 27,
    "plan_id": 1,
    "nodes": 2,
    "type": "production",
    "created_at": "2013-01-25T08:18:39Z",
    "updated_at": "2013-01-28T16:45:24Z",
    "available_since": "2013-01-28T16:46:22Z",
    "terminated_at": "2013-01-28T17:45:33Z",
    "running_jobs_count": 0,
    "terminate_on_idle": false,
    "time_to_idle": 3600,
    "terminated_on_idle": false,
    "region": "amazon-web-services::us-east-1",
    "zone": "us-east-1b",
    "master_instance_type": "m3.xlarge",
    "slave_instance_type": "m3.xlarge",
    "master_spot_price": null,
    "slave_spot_price": null,
    "master_spot_percentage": null,
    "slave_spot_percentage": null,
    "allow_fallback": true,
    "stack": "white-everest",
    "idle_since": "2013-03-03T13:06:51Z",
    "url": "https://api.xplenty.com/xplenation/api/clusters/99",
    "html_url": "https://xplenty.com/xplenation/clusters/99",
    "creator":
    {
        "type":"Schedule",
        "display_name": "Schedule 1",
        "id":1,
        "url": "https://api.xplenty.com/xplenation/api/schedules/1",
        "html_url": "https://xplenty.com/xplenation/schedules/1"
    }
  },
  {
    "id": 98,
    "name": "Daily Outliers Test #101",
    "description": "Daily Outliers Test",
    "status": "terminated",
    "owner_id": 27,
    "plan_id": 1,
    "nodes": 2,
    "type": "production",
    "created_at": "2013-01-25T08:17:56Z",
    "updated_at": "2013-01-28T16:45:14Z",
    "available_since": "2013-01-28T08:23:12Z",
    "terminated_at": "2013-01-28T16:45:14Z",
    "running_jobs_count": 0,
    "terminate_on_idle": false,
    "time_to_idle": 3600,
    "terminated_on_idle": false,
    "region": "amazon-web-services::us-east-1",
    "zone": "us-east-1d",
    "master_instance_type": "m3.xlarge",
    "slave_instance_type": "m3.xlarge",
    "master_spot_price": null,
    "slave_spot_price": null,
    "master_spot_percentage": null,
    "slave_spot_percentage": null,
    "allow_fallback": true,
    "stack": "white-everest",
    "idle_since": "2013-03-03T13:06:51Z",
    "url": "https://api.xplenty.com/xplenation/api/clusters/98",
    "html_url": "https://xplenty.com/xplenation/clusters/98",
    "bootstrap_actions": [{
      "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
      "args": ["arg1", "arg2"]
    }, {
      "script_path": "http://xplenty.s3.amazonaws.com/bootstrap-actions/file1.tar.gz",
      "args": ["arg1"]
    }]
  },
  {
    "id": 97,
    "name": "Daily Outliers Test #102",
    "description": "Daily Outliers Test",
    "status": "terminated",
    "owner_id": 27,
    "plan_id": null,
    "nodes": 0,
    "type": "sandbox",
    "created_at": "2013-01-25T07:36:04Z",
    "updated_at": "2013-01-25T07:45:19Z",
    "available_since": "2013-01-25T07:40:02Z",
    "terminated_at": "2013-01-25T07:45:19Z",
    "running_jobs_count": 0,
    "terminate_on_idle": true,
    "time_to_idle": 3600,
    "terminated_on_idle": true,
    "region": "amazon-web-services::us-east-1",
    "zone": "us-east-1c",
    "master_instance_type": "m3.xlarge",
    "slave_instance_type": "m3.xlarge",
    "master_spot_price": null,
    "slave_spot_price": null,
    "master_spot_percentage": null,
    "slave_spot_percentage": null,
    "allow_fallback": true,
    "stack": "white-everest",
    "idle_since": "2013-03-03T13:06:51Z",
    "url": "https://api.xplenty.com/xplenation/api/clusters/97",
    "html_url": "https://xplenty.com/xplenation/clusters/97"
  }
]
```
