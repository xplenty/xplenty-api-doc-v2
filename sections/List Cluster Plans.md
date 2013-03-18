## List Cluster Plans

### Description
A cluster plan is a definition of a cluster type, which includes the number of nodes in the cluster and its pricing. Cluster plan details can be viewed in the Xplenty web application.
This call returns a list of all the available cluster plans, including the name and numeric ID of each plan. After you've determined which cluster plan is appropriate for your needs, use this call to retrieve the cluster plan ID. The cluster plan ID can then be used when creating a new cluster (see [Create Cluster](https://github.com/xplenty/xplentydoc/wiki/Create-Cluster)).

### Input Parameters
None.

### Request (Curl Call)
```shell
curl -X GET -H 'Accept: application/vnd.xplenty+json' -u <APIkey>: 'https://api.xplenty.com/_<accountID>_/api/cluster_plans'
```
### Response Example
```json
    [
        {
            "id": 1,
            "name": "Free"
        },
        {
            "id": 2,
            "name": "Medium"
        },
        {
            "id": 3,
            "name": "Large"
        },
        {
            "id": 4,
            "name": "Extra Large"
        }
    ]
```
