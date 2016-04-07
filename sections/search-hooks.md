## Search Hooks

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
* **type**

Please read the document describing hooks:

* [Web Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/web-hook.md)
* [Slack Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/slack-hook.md)
* [Hip Chat Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/hip-chat-hook.md)
* [Email Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/email-hook.md)
* [Pager Duty Hook](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/hooks/pager-duty-hook.md)



### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
q|Y| |Terms, e.g. `name:"test hook" type:slack`
sort|N|"relevance"|Possible values are `modified`, `created` or `relevance`. The hook list will be sorted by the hooks' `updated_at`, `created_at` attributes or relevance of the search results.
direction|N|"desc"|Possible values are: `asc`, `desc`. The hooks will be sorted in ascending or descending order of the `sort` attribute.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/hooks/search" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "q":"name:\"test hook\" type:slack",
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
    "id": 1,
    "salt": "2db5b8725e2d86aba40d43f6e403bdf483b8535a3d0011d34b3687140b52bc8c",
    "active": true,
    "type": "web",
    "settings": {
      "url": "http://my.service.com/notifications",
      "insecure_ssl": false,
      "basic_auth": true
    },
    "events": ["job.submitted", "cluster.terminated"]
  },
  {
    "id": 2,
    "salt": "56f07c3f04d37c097d6a2c22dcefa6f0fc1610cba08beb7c293988f42cb8ed14",
    "active": true,
    "type": "web",
    "settings": {
      "url": "http://my.service.com/notifications",
      "insecure_ssl": false,
      "basic_auth": true
    },
    "events": ["job.submitted", "cluster.terminated"]
  }
]
```
