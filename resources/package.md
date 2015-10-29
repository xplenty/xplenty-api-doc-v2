An Xplenty **package** is a data flow definition that you define in the Xplenty web application.
It describes the data to process (location, schema, fields), data manipulation to perform, and the output destinations (location, schema). The package's workflow is implemented by jobs.

### Package Attributes

* **id** - the numeric package ID
* **name** - the name given to the package upon creation
* **description** - the description given to the package upon creation
* **variables** - the list of package variables
* **owner_id** - the numeric user id of the package owner
* **created_at** - the date and time the package was created
* **updated_at** - the date and time the package was last updated 
* **url** - the package resource URL (API)
* **html_url** - the package resource URL (Web UI)
* **status** - the package status. Possible values are:
  * **active**
  * **archived**