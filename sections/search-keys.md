## Search Public Keys

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


### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
q|Y| |Terms, e.g. `name:"key 1"`
sort|N|"relevance"|Possible values are `id`, `updated`, `created` or `name`. The key list will be sorted by the keys' `id`, `updated_at`, `created_at`, `name` attributes or relevance if no sort parameter is specified.
direction|N|"asc"|Possible values are: `asc`, `desc`. The keys will be sorted in ascending or descending order of the `sort` attribute.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/user/keys/search" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "q":"name:\"key 1\"",
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
    "id":1,
    "comment":"sample@example.com",
    "name":"My public key",
    "fingerprint":"10:37:49:10:f2:d5:f2:e2:48:e5:66:9f:1d:2f:87:96",
    "created_at":"2015-02-27T07:55:39Z",
    "updated_at":"2015-02-27T07:55:39Z",
    "url":"https://api.xplenty.com/user/keys/1"
  },
  {
    "id":2,
    "comment":"sample2@example.com",
    "name":"My public key",
    "fingerprint":"33:35:49:12:f2:d5:f2:e2:48:e5:66:9f:1d:2f:87:96",
    "created_at":"2015-02-27T07:55:39Z",
    "updated_at":"2015-02-27T07:55:39Z",
    "url":"https://api.xplenty.com/user/keys/2"
  }
]
```
