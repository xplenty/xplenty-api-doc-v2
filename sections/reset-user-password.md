## Reset User Password

### Description
Resets [user](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/user.md) password.

### Input Parameters
|Name|Required?|Default|Description|
|----|---------|-------|-----------|
|email|Y| |The email of the user.


### Request (Curl Call) Example
```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/user_password" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "email" : "sample@email.com"
  }'
```

### Response Example
```HTTP
HTTP/1.1 201 Created
```
