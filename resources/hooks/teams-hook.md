An Xplenty **Microsoft Teams hook** is a kind of notification that is posted as an Adaptive Card to a Microsoft Teams channel when the state of a resource ([cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md), [job](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/job.md) or schedule) changes. Types of notifications can be specified with the **events** variable.

The hook delivers to a Teams **Workflows** webhook (the "Send webhook alerts to a channel" workflow template). Office 365 connector Incoming Webhook URLs (`webhook.office.com`) are retired by Microsoft and are rejected.

### Microsoft Teams Hook Attributes

* **id** - the numeric hook ID
* **type** - `teams`
* **name** - name of the hook, default: `Microsoft Teams`
* **active** - indicates whether the Microsoft Teams hook is active
* **settings** - settings specific for the Microsoft Teams hook. It contains the following attributes:
  * **url** - the Teams Workflows webhook URL. Required. It must be an `https` URL on port 443, without user credentials, on a host ending in `.powerplatform.com`, `.powerautomate.com` or `.logic.azure.com`; any other URL is rejected with `422 Unprocessable Entity`. The URL embeds a signature (`sig=`) that allows posting to the channel, so treat it as a secret. It is stored encrypted.
* **events** - list of notification events. Possible values:
  * **job** - all job events
  * **job.submitted**
  * **job.started**
  * **job.stopped**
  * **job.completed**
  * **job.failed**
  * **cluster** - all cluster events
  * **cluster.requested**
  * **cluster.available**
  * **cluster.terminated**
  * **cluster.idled**
  * **cluster.error**
  * **schedule** - all schedule events
  * **schedule.created**
  * **schedule.enabled**
  * **schedule.disabled**
  * **schedule.deleted**
  * **schedule.skipped**
* **salt** - hash generated using SHA-1 from string created by concatenation of the following fields:
  * **id**
  * **event name**
  * **url**
  * **salt**

### Delivery

* Any 2xx response from Teams counts as delivered (Workflows webhooks answer `202 Accepted`).
* Timeouts, connection errors, `429` and `5xx` responses are retried up to 4 times with increasing backoff. A `Retry-After` header is honoured, up to 10 minutes.
* Other `4xx` responses (for example `404` when the workflow was deleted, or `401`/`403` when the signature is rejected) are not retried.
* Redirects are not followed.

### Create Example

```shell
$ curl -X POST -u api_key: "https://api.xplenty.com/:account_id/api/hooks" \
  -H "Accept: application/vnd.xplenty+json; version=2" \
  -H "Content-Type: application/json" \
  -d '{
    "type": "teams",
    "name": "Data team alerts",
    "settings": {
      "url": "https://<environment>.environment.api.powerplatform.com/powerautomate/automations/direct/workflows/<id>/triggers/manual/paths/invoke?api-version=1&sig=<signature>"
    },
    "events": ["job.failed", "cluster.error"]
  }'
```
