## List Product Updates

### Description
This call returns list of latest product announcements.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/product_updates" \
  -H "Accept: application/vnd.xplenty+json, version=2" \
  -H "Content-Type: application/json"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id": 1,
    "title": "Xplenty Now Provides Cross Join Between Dataflows",
    "created_at": "2015-05-18T11:13:55Z",
    "body": "## Cross Join Between Dataflows!\n Xplenty now supports the capability to join dataflows using non-equality conditions to compare values between the dataflows. This is done using the new cross join component to define the data sources to join and then applying a filter to the joined dataflow.\n\nFor example, to match people in dataflow1 with younger people in dataflow2 you simply:\n\nCross join dataflow1 with dataflow2\nFilter the resulting dataflow with a condition that age from dataflow1 is greater than age from dataflow2\nThere you have a new feature to make your data processing that much smoother.",
    "body_html": "<p>Xplenty now supports the capability to join dataflows using non-equality conditions to compare values between the dataflows. This is done using the new cross join component to define the data sources to join and then applying a filter to the joined dataflow.</p>\n\n<p>For example, to match people in dataflow1 with younger people in dataflow2 you simply:</p>\n\n<p>Cross join dataflow1 with dataflow2\nFilter the resulting dataflow with a condition that age from dataflow1 is greater than age from dataflow2\nThere you have a new feature to make your data processing that much smoother.</p>\n",
    "body_text": "Cross Join Between Dataflows!\nXplenty now supports the capability to join dataflows using non-equality conditions to compare values between the dataflows. This is done using the new cross join component to define the data sources to join and then applying a filter to the joined dataflow.\nFor example, to match people in dataflow1 with younger people in dataflow2 you simply:\nCross join dataflow1 with dataflow2\nFilter the resulting dataflow with a condition that age from dataflow1 is greater than age from dataflow2\nThere you have a new feature to make your data processing that much smoother.\n",
    "likes": 0
  },
  {
    "id": 2,
    "title": "Xplenty Now Provides Cross Join Between Dataflows",
    "created_at": "2015-05-18T11:13:55Z",
    "body": "## Cross Join Between Dataflows!\n Xplenty now supports the capability to join dataflows using non-equality conditions to compare values between the dataflows. This is done using the new cross join component to define the data sources to join and then applying a filter to the joined dataflow.\n\nFor example, to match people in dataflow1 with younger people in dataflow2 you simply:\n\nCross join dataflow1 with dataflow2\nFilter the resulting dataflow with a condition that age from dataflow1 is greater than age from dataflow2\nThere you have a new feature to make your data processing that much smoother.",
    "body_html": "<p>Xplenty now supports the capability to join dataflows using non-equality conditions to compare values between the dataflows. This is done using the new cross join component to define the data sources to join and then applying a filter to the joined dataflow.</p>\n\n<p>For example, to match people in dataflow1 with younger people in dataflow2 you simply:</p>\n\n<p>Cross join dataflow1 with dataflow2\nFilter the resulting dataflow with a condition that age from dataflow1 is greater than age from dataflow2\nThere you have a new feature to make your data processing that much smoother.</p>\n",
    "body_text": "Cross Join Between Dataflows!\nXplenty now supports the capability to join dataflows using non-equality conditions to compare values between the dataflows. This is done using the new cross join component to define the data sources to join and then applying a filter to the joined dataflow.\nFor example, to match people in dataflow1 with younger people in dataflow2 you simply:\nCross join dataflow1 with dataflow2\nFilter the resulting dataflow with a condition that age from dataflow1 is greater than age from dataflow2\nThere you have a new feature to make your data processing that much smoother.\n",
    "likes": 0
  }
]
```
