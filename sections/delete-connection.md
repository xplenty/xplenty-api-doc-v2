## Delete Account Connection

### Description
This call deletes the given connection.

Use this call when the connection is no longer needed.

### Notes
Please note that deleting the connection will invalidate all items referencing it.

The details returned for the deleted connection are:

* **id** - the connection's numeric identifier
* **name** - the name given to the connection upon creation
* **created_at** - the date and time the connection was created
* **updated_at** - the date and time the connection was last updated
* **type** - the type of connection

### Input Parameters
The **connection type** and **connection resource ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json, version=2" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/connections/<connectionType>/<connectionID>"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "id":234,
  "name":"Amazon S3 sample connection",
  "created_at":"2015-02-16T07:58:52Z",
  "updated_at":"2015-02-16T07:58:52Z",
  "type":"s3"
}
```
