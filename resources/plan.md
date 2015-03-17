An account **plan** defines price and limits for members, clusters, etc.

## Plan Attributes

* **id** - the plan's string identifier
* **name** - the descriptive name of the plan
* **description** - the description of the plan
* **price_cents**
* **price_currency** - the currency of the plan
* **price_unit** - possible values:
  * **year**
  * **month**
  * **day**
  * **hour**
* **cluster_node_hours_included**
* **cluster_node_hours_limit**
* **cluster_node_price_cents**
* **cluster_node_price_currency**
* **cluster_node_price_unit**
* **cluster_nodes_limit**
* **cluster_size_limit**
* **clusters_limit**
* **sandbox_clusters_limit**
* **sandbox_node_hours_included**
* **sandbox_node_hours_limit**
* **members_limit** - the maximum number of members for an account
* **position**
* **created_at** - the date and time the plan was created
* **updated_at** - the date and time the plan was last updated