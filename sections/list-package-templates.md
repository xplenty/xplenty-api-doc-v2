## List Package Templates

### Description
List [package templates](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/packate_template.md) that are available for the authenticated user.
You can use template to create new package with predefined settings.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/packages/templates" \
  -H "Accept: application/vnd.xplenty+json; version=2"
```
### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 1,
    "name": "Test template 1",
    "description": "Template description",
    "position": 0,
    "author": {
      "id": 1,
      "name": "Xplenty Admin",
      "avatar_url": "http://gravatar.com/avatar/27f3cadb9b61dd9dd567a1c6b3d4028b.png?d=retro&s=140"
    }
  },
  {
    "id": 2,
    "name": "Test template 2",
    "description": "Template description",
    "position": 1,
    "author": {
      "id": 1,
      "name": "Xplenty Admin",
      "avatar_url": "http://gravatar.com/avatar/27f3cadb9b61dd9dd567a1c6b3d4028b.png?d=retro&s=140"
    }
  }
]
```
