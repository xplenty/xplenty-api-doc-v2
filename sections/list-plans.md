## List Account Plans

### Description
List [plans](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/plan.md) that are available for an account.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/:account_id/api/plans" \
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
    "id":"free-trial",
    "name":"Free Trial",
    "description":"Free Trial",
    "price_cents":0,
    "price_currency":"USD",
    "price_unit":"month",
    "cluster_node_hours_included":0,
    "cluster_node_hours_limit":-1,
    "cluster_node_price_cents":0,
    "cluster_node_price_currency":"USD",
    "cluster_node_price_unit":"hour",
    "cluster_nodes_limit":0,
    "cluster_size_limit":0,
    "clusters_limit":0,
    "sandbox_clusters_limit":0,
    "sandbox_node_hours_included":0,
    "sandbox_node_hours_limit":-1,
    "members_limit":1,
    "position":2,
    "created_at":"2015-03-17T14:40:26Z",
    "updated_at":"2015-03-17T14:40:26Z"
  },
  {
    "id":"free",
    "name":"Free",
    "description":"Free",
    "price_cents":0,
    "price_currency":"USD",
    "price_unit":"month",
    "cluster_node_hours_included":0,
    "cluster_node_hours_limit":-1,
    "cluster_node_price_cents":0,
    "cluster_node_price_currency":"USD",
    "cluster_node_price_unit":"hour",
    "cluster_nodes_limit":0,
    "cluster_size_limit":0,
    "clusters_limit":0,
    "sandbox_clusters_limit":0,
    "sandbox_node_hours_included":0,
    "sandbox_node_hours_limit":-1,
    "members_limit":1,
    "position":1,
    "created_at":"2015-03-17T14:40:26Z",
    "updated_at":"2015-03-17T14:40:26Z"
  },
  {
    "id":"basic",
    "name":"Basic",
    "description":"Basic Plan",
    "price_cents":0,
    "price_currency":"USD",
    "price_unit":"month",
    "cluster_node_hours_included":0,
    "cluster_node_hours_limit":-1,
    "cluster_node_price_cents":0,
    "cluster_node_price_currency":"USD",
    "cluster_node_price_unit":"hour",
    "cluster_nodes_limit":0,
    "cluster_size_limit":0,
    "clusters_limit":0,
    "sandbox_clusters_limit":0,
    "sandbox_node_hours_included":0,
    "sandbox_node_hours_limit":-1,
    "members_limit":1,
    "position":0,
    "created_at":"2015-03-17T14:40:26Z",
    "updated_at":"2015-03-17T14:40:26Z"
  }
]
```
