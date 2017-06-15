An Xplenty **delivery** is a blueprint for a set of resources which automates the task of delivering data from one place to another.

### Delivery Attributes

* **id** the numeric delivery ID
* **name** the name given to the delivery upon creation
* **description** the description given to the delivery upon creation
* **status** the delivery's status. Possible values are:
    * **idle**
    * **enabled**
    * **disabled**
* **interval_amount** number of interval units between delivery's task executions
* **interval_unit** Possible values are:
    * **minutes**
    * **hours**
    * **days**
    * **weeks**
    * **months**
* **source** a source contains the following fields:
    * **connection** a valid connection to be used as a source
        * **id** the connection's numeric identifier
        * **type** the connection's type (e.g `salesforce`, `adwords`, `analytics`)
    * **properties** key value pairs of source specific properties
* **destination** a destination contains the following fields:
    * **connection** a valid connection to be used as a destination
        * **id** the connection's numeric identifier
        * **type** the connection's type (e.g `redshift`, `bigquery`)
    * **properties** key value pairs of destination specific properties (e.g `schema`)
* **created_at** the date and time the delivery was created
* **updated_at** the date and time the delivery was updated
* **url** the delivery resource URL (API)