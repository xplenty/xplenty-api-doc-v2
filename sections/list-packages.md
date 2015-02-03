## List Packages

### Description
This call returns information for the list of packages that were created by users in your account.
You can use this information to monitor your packages.

The details returned for each package are:

* **id** - the numeric package ID
* **name** - the name given to the package upon creation
* **description** - the description given to the package upon creation
* **variables** - the list of package variables
* **owner_id** - the numeric user id of the package owner
* **created_at** - the date and time the package was created
* **updated_at** - the date and time the package was last updated
* **url** - the package resource URL

### Input Parameters
None

### Request (Curl Call) Syntax
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/packages"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 2373,
    "name": "AWS CloudFront Log Analysis",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T07:09:18Z",
    "updated_at": "2014-04-13T19:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2373"
  },
  {
    "id": 2374,
    "name": "AWS CloudFront Log Analysis 2",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T08:09:18Z",
    "updated_at": "2014-04-13T20:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2374"
  }
]
```
