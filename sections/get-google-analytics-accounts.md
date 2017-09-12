## Get Google Analytics accounts.

### Description
Informations about all accounts accessible by a given Google Analytics connection.

### Input Parameters
Required parameter is the **connection_id**.

|Name|Required?|Default|Description|
|----|---------|-------|-----------|
force_fetch|N|false|determines if caching should be bypassed


### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/connections/metadata/analytics/:connection_id/accounts" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "name": "Account 1",
    "id": "12345678",
    "properties": [
      {
        "name": "Web Property 1",
        "id": "UA-12345678-1",
        "views": [
          {
            "name": "All Web Sites",
            "id": "5123412"
          }
        ]
      },
      {
        "name": "Web Property 2",
        "id": "UA-12345678-2",
        "views": [
          {
            "name": "All Web Sites",
            "id": "41233512"
          }
        ]
      }
    ]
  },
  {
    "name": "Account 2",
    "id": "22345678",
    "properties": [
      {
        "name": "Web Property 1",
        "id": "UA-5123412-1",
        "views": [
          {
            "name": "All Web Sites",
            "id": "5123412"
          }
        ]
      },
      {
        "name": "Web Property 2",
        "id": "UA-41233512-2",
        "views": [
          {
            "name": "All Web Sites",
            "id": "41233512"
          }
        ]
      }
    ]
  }
]
```
