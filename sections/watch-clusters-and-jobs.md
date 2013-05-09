# Watch Jobs and Clusters

## Description
You can choose to "watch" cluster or job items that you or other users have created. 
If you're watching an item, you'll receive notifications on important updates.

**For job items**, you'll receive notifications when the job reaches the "completed", "failed" or "stopped" statuses.

**For cluster items**, you'll receive notifications when the cluster reaches the "available", "terminated" or "error" statuses,
and also when a new job is run on the cluster.

The notifications can be sent as email messages, or as messages which you can view in the Xplenty web application.
You can change the method of notification for your user in [notification settings page](https://app.xplenty.com/settings/notifications).

Users can add or remove themselves from the watcher list of specific items, and can retrieve the list of watchers for a specific item.
Below are descriptions of the API calls that add, delete and retrieve watchers for clusters and jobs.

## Notes
By default, the user who created a cluster or job item will be a watcher of that item.

## Watch Cluster
This call adds the calling user as a watcher of the specified cluster.

### Input Parameters
* **cluster_id** - the ID of the cluster to watch

### Request (Curl Call)
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json" -u <APIkey>: 'https://api.xplenty.com/<accountID>/api/clusters/{cluster_id}/watchers'
```

### Response Example
```json
{"created_at":"2013-04-09T11:19:20+03:00","cluster_url":"https://api.xplenty.com/xplenation/api/clusters/370"}
```

## Stop Watching Cluster
This call removes the calling user from the watcher list of the specified cluster.

### Input Parameters
* **cluster_id** - the ID of the cluster to stop watching

### Request (Curl Call)
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/clusters/{cluster_id}/watchers"
```

### Response
Header 204.

## Get Cluster Watchers
This call retrieves the list of users watching the specified cluster.

### Input Parameters
* **cluster_id** - the ID of the cluster to whose watchers you want to retrieve

### Request (Curl Call)
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: 'https://api.xplenty.com/<accountID>/api/clusters/{cluster_id}/watchers'
```

### Response Example
```json
{"id":1,"display_name":"Xplenty"}
```

## Watch Job
This call adds the calling user as a watcher of the specified job.

### Input Parameters
* **job_id** - the ID of the job to watch

### Request (Curl Call)
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json" -u <APIkey>: 'https://api.xplenty.com/<accountID>/api/jobs/{job_id}/watchers'
```

### Response Example
```json
{"created_at":"2013-04-09T11:28:27+03:00","job_url":"https://api.xplenty.com/xplenation/api/jobs/492"}
```

## Stop Watching Job
This call removes the calling user from the watcher list of the specified job.

### Input Parameters
* **job_id** - the ID of the job to stop watching

### Request (Curl Call)
```shell
curl -X DELETE -H "Accept: application/vnd.xplenty+json" -u <APIkey>: 'https://api.xplenty.com/<accountID>/api/jobs/{job_id}/watchers'
```

### Response
Header 204.

## Get Job Watchers
This call retrieves the list of users watching the specified job.

### Input Parameters
* **job_id** - the ID of the job to whose watchers you want to retrieve

### Request (Curl Call)
```shell
curl -X GET -H "Accept: application/vnd.xplenty+json" -u api_key: "https://api.xplenty.com/xplenation/api/jobs/{job_id}/watchers"
```

### Response Example
```json
{"id":1,"display_name":"Xplenty"}
```
