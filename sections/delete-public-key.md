## Delete Public Key

### Description
This call deletes the given [public key](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/public-key.md). Use this action when the key is no longer needed.

### Input Parameters
The **key ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
$ curl -X DELETE -u api_key: "https://api.xplenty.com/user/keys/:key_id" \
  -H "Accept: application/vnd.xplenty+json, version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":123,
  "comment":"sample@example.com",
  "name":"My public key",
  "fingerprint":"10:37:49:10:f2:d5:f2:e2:48:e5:66:9f:1d:2f:87:96",
  "created_at":"2015-02-27T07:55:39Z",
  "updated_at":"2015-02-27T07:55:39Z",
  "url":"http://api.xplenty.com/user/keys/123"
}
```
