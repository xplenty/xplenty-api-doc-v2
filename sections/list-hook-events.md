## List supported Hook Events

### Description
This call returns list of supported Hook Events.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/hook_events" \
  -H "Accept: application/vnd.xplenty+json, version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "id":"job",
    "group_name":"Job",
    "name":"All Job Notifications"
  },
  {
    "id":"job.submitted",
    "group_name":"Job",
    "name":"Job Submitted"
  },
  {
    "id":"job.started",
    "group_name":"Job",
    "name":"Job Started"
  },
  {
    "id":"job.stopped",
    "group_name":"Job",
    "name":"Job Stopped"
  },
  {
    "id":"job.completed",
    "group_name":"Job",
    "name":"Job Completed"
  },
  {
    "id":"job.failed",
    "group_name":"Job",
    "name":"Job Failed"
  },
  {
    "id":"cluster",
    "group_name":"Cluster",
    "name":"All Cluster Notifications"
  },
  {
    "id":"cluster.requested",
    "group_name":"Cluster",
    "name":"Cluster Requested"
  },
  {
    "id":"cluster.available",
    "group_name":"Cluster",
    "name":"Cluster Available"
  },
  {
    "id":"cluster.terminated",
    "group_name":"Cluster",
    "name":"Cluster Terminated"
  },
  {
    "id":"cluster.idled",
    "group_name":"Cluster",
    "name":"Cluster Idled"
  },
  {
    "id":"cluster.error",
    "group_name":"Cluster",
    "name":"Cluster Error"
  }
]
```