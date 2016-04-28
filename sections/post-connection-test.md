## Post Connection test.

### Description
Checks if connection is available.
List [connections](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/connection.md) that are accessible by the authenticated user.


### Input Parameters
Required parameter is the **id** which is the connection id and **type** of the connection. Values of types are listed above.
Possible **type** is also ```curl```, in that case, **id** is not required.

### Request (Curl Call) Syntax
```shell
$ curl -X POST -u api_key: "/:account_id/api/connections/:type/:id/test" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

```shell
$ curl -X POST -u api_key: "/:account_id/api/connections/curl/test" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "false"
}
```

```json
{
  "true"
}
```

