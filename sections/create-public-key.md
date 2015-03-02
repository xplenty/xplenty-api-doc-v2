## Create Public Key

### Description
This call creates a new public key. Use this call when you need to add new key to your user account.

The details returned for created key are:

* **id** - the key's numeric identifier
* **comment** - the comment given upon creation. It is last item of the passed key (e.g. email)
* **fingerprint** - fingerprint of the key
* **name** - name of the key
* **url** - API url for key
* **created_at** - the date and time the member was created
* **updated_at** - the date and time the member was last updated

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|public_key|Y| |Public key which contains information about type of encryption at the beginning of string, like: 'ssh-rsa'.
|name|N| |Name of the public key. Comment's value will be copied to this field if it is empty.

### Request (Curl Call) Example
```shell
curl -X POST -H "Content-Type: application/json" -H "Accept: application/vnd.xplenty+json, version=2" \
    -u <APIkey>: "https://api.xplenty.com/user/keys" \
    -d '{
      "public_key" : "<publicKey>",
      "name" : "<name>"
    }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```

```json
{
  "id":123,
  "comment":"sample@example.com",
  "name":"My public key"
  "fingerprint":"10:37:49:10:f2:d5:f2:e2:48:e5:66:9f:1d:2f:87:96",
  "url":"http://api.xplenty.com/user/keys/123"
  "created_at":"2015-02-27T07:55:39Z",
  "updated_at":"2015-02-27T07:55:39Z"
}
```
