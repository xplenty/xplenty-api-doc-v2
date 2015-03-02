## Delete Public Key

### Description
This call deletes the given public key. Use this action when the key is no longer needed.

The details returned for removed key are:

* **id** - the key's numeric identifier
* **comment** - the comment given upon creation. It is last item of the passed key (e.g. email)
* **fingerprint** - fingerprint of the key
* **name** - name of the key
* **url** - API url for key
* **created_at** - the date and time the key was created
* **updated_at** - the date and time the key was last updated

### Input Parameters
The **key ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json, version=2" -u api_key: "https://api.xplenty.com/user/keys/:id"
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
  "url":"http://api.xplenty.com/user/keys/123",
  "created_at":"2015-02-27T07:55:39Z",
  "updated_at":"2015-02-27T07:55:39Z"
}
```
