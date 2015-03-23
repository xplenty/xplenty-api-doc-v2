## List Public Keys

### Description
List authenticated user's [public keys](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/public-key.md).
Optionally, you can supply the input parameters to determine the order by which the list will be sorted.

### Input Parameters

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
sort|N|"created"|Possible values are  ```updated```, ```created```, ```name```.
direction|N|"asc"|Possible values are: ```asc```, ```desc```. The keys will be sorted in ascending or descending order of the "sort" attribute.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/user/keys" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json"
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
