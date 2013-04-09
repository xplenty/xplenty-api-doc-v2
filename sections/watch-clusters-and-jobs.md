# Watch Jobs and Clusters

## Description
You can choose to "watch" cluster or job items that you or other users have created. 
If you're watching an item, you'll receive notifications when the items reach certain statuses.

For job items, you'll receive notifications when the job reaches the "completed", "failed" or "stopped" statuses.

For cluster items, you'll receive notifications when the cluster reaches the "available", "terminated" or "error" statuses,
and also when a new job is run on the cluster.

The notifications can be sent as email messages, or as messages which you can view in the Xplenty web application.
You can configure the method of notification in the Xplenty web application.

Users can add or delete themselves from the watcher list of specific items, and can retrieve the list of watchers for a specific item.
Below are descriptions of the API calls that add, delete and retrieve watchers for clusters and jobs.

## Notes
By default, the user who created a cluster or job item will be a watcher of that item.

## Add User as Cluster Watcher
This call adds the calling user as a watcher of the specified cluster.

### Input Parameters
* **cluster_id** - the ID of the cluster to watch

### Request (Curl Call)
```shell
curl -X POST   		-H "Accept: application/vnd.xplenty+json" -u api_key: "https://api-staging.xplenty.com/xpd1/api/clusters/{cluster_id}/watchers"
```

### Response Example
```json

```

