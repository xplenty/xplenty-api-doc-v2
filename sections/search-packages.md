## Search Packages

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
* **user**
* **created**
* **modified**

Free text (not assigned to any attribute) will search in name and description. They will be joined with OR.

Please read the document describing [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md) for other details.


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
q|Y| |Terms, e.g. `name:"package 1" test package`
sort|N|"relevance"|Possible values are `modified`, `created` or `relevance`. The package list will be sorted by the packages' `updated_at`, `created_at` attributes or relevance of the search results.
direction|N|"desc"|Possible values are: `asc`, `desc`. The packages will be sorted in ascending or descending order of the `sort` attribute.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/packages/search" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "q":"name:\"package 1\" test package",
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
    "id": 2373,
    "name": "AWS CloudFront Log Analysis",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T07:09:18Z",
    "updated_at": "2014-04-13T19:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2373",
    "html_url":"https://xplenty.com/xplenation/packages/2373",
    "status":"active"
  },
  {
    "id": 2374,
    "name": "AWS CloudFront Log Analysis 2",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T08:09:18Z",
    "updated_at": "2014-04-13T20:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2374",
    "html_url":"https://xplenty.com/xplenation/packages/2374",
    "status":"active"
  }
]
```
