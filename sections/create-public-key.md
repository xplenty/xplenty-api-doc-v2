## Create Public Key

### Description
This call creates a new public key. Use this call when you need to add new key to your user account.

The details returned for created key are:

* **id** - the key's numeric identifier
* **comment** - the comment given upon creation. It is last item of the passed key (e.g. email)
* **fingerprint** - fingerprint of the key
* **name** - name of the key
* **url** - API url for key
* **created_at** - the date and time the key was created
* **updated_at** - the date and time the key was last updated

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|public_key|Y| |Public key which contains information about type of encryption at the beginning of string, like: 'ssh-rsa'.
|name|N| |Name of the public key. Comment's value will be copied to this field if it is empty.

### Request (Curl Call) Example
```shell
curl -X POST -H "Content-Type: application/json" -H "Accept: application/vnd.xplenty+json, version=2" \
    -u api_key: "https://api.xplenty.com/user/keys" \
    -d '{
      "public_key" : "ssh-dss AAAAB3NzaC1kc3MAAACBAJ7gwhsEDUOw1AkGD/9OhmyLVpDezUkAKUvSF//hdNX/uFNxqpnqunHRj1vhenM0CklrWDmgBe7K1tnPZzNb0kXfLDaBFkpuCfQLazWcTHUao5YvW4Ze8tzcPaNOrlg6Dlow1VfrFoX9zhjGKbPKUQlSKiRTf3mfB7MyWr3xNQ59AAAAFQCTGtEsp3X06DpK0X25zJXlGkhB+wAAAIBDHW10fingslAEmmp4cSKn7alYIannhtML7bHP62HaSJTV4jcCw88ZKU9sRp7D+t5qU0YaoTjvFOfVaiuekEM5Ch2A3RI+WkcmFUjP1+UFR6DKwUgCIjlokbwEgveEpttOBAODhD6OlL1977EUECwXLprYHoP37yHVqUfc78ui+gAAAIBR1dhKoMADWce31WA0arJKREJeiP0IEaR5xEEnclFkvRRhK71vszCWMeemjUPeahqgdVur4LQ2iX43KfESX8jpK3lDiRF4zsv8+2SeQIwi6XbRR0SpyuOVCtRtvQAbw/3n76htDtc9zDVw0qPrTjUEtONt9AE4McqF7V44wpwaYQ== owner@example.com",
      "name" : "My publick key"
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
  "name":"My public key",
  "fingerprint":"10:37:49:10:f2:d5:f2:e2:48:e5:66:9f:1d:2f:87:96",
  "url":"http://api.xplenty.com/user/keys/123",
  "created_at":"2015-02-27T07:55:39Z",
  "updated_at":"2015-02-27T07:55:39Z"
}
```
