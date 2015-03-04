## Create Public Key

### Description
This call creates a new [public key](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/public-key.md) associated with the authenticated user.

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|name|N| |Name to assign to the new public key. Public key comment will be used if left blank.
|public_key|Y| |SSH Public key which contains information about type of encryption at the beginning of string, like: 'ssh-rsa'.


### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/user/keys" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "name" : "My public key",
    "public_key" : "ssh-rsa AAAAB3NzaC1kc3MAAACBAJ7gwhsEDUOw1AkGD/9OhmyLVpDezUkAKUvSF//hdNX/uFNxqpnqunHRj1vhenM0CklrWDmgBe7K1tnPZzNb0kXfLDaBFkpuCfQLazWcTHUao5YvW4Ze8tzcPaNOrlg6Dlow1VfrFoX9zhjGKbPKUQlSKiRTf3mfB7MyWr3xNQ59AAAAFQCTGtEsp3X06DpK0X25zJXlGkhB+wAAAIBDHW10fingslAEmmp4cSKn7alYIannhtML7bHP62HaSJTV4jcCw88ZKU9sRp7D+t5qU0YaoTjvFOfVaiuekEM5Ch2A3RI+WkcmFUjP1+UFR6DKwUgCIjlokbwEgveEpttOBAODhD6OlL1977EUECwXLprYHoP37yHVqUfc78ui+gAAAIBR1dhKoMADWce31WA0arJKREJeiP0IEaR5xEEnclFkvRRhK71vszCWMeemjUPeahqgdVur4LQ2iX43KfESX8jpK3lDiRF4zsv8+2SeQIwi6XbRR0SpyuOVCtRtvQAbw/3n76htDtc9zDVw0qPrTjUEtONt9AE4McqF7V44wpwaYQ== owner@example.com"
  }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```

```json
{
  "id":123,
  "name":"My public key",
  "comment":"owner@example.com",
  "fingerprint":"10:37:49:10:f2:d5:f2:e2:48:e5:66:9f:1d:2f:87:96",
  "created_at":"2015-02-27T07:55:39Z",
  "updated_at":"2015-02-27T07:55:39Z",
  "url":"http://api.xplenty.com/user/keys/123"
}
```
