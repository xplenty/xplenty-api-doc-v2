## Get Public Key

### Description
This call returns the details of the user's public key.

The details returned for the key are:

* **id** - the key's numeric identifier
* **comment** - the comment given upon creation. It is last item of the passed key (e.g. email)
* **fingerprint** - fingerprint of the key
* **url** - API url for key
* **created_at** - the date and time the member was created
* **updated_at** - the date and time the member was last updated

### Input Parameters
The **key ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/user/keys/<keyID>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":123,
  "comment":"sample@example.com",
  "fingerprint":"10:37:49:10:f2:d5:f2:e2:48:e5:66:9f:1d:2f:87:96",
  "created_at":"2015-02-27T07:55:39Z",
  "updated_at":"2015-02-27T07:55:39Z"
}
```
