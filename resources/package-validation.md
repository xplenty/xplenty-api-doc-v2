An Xplenty **package validation** contains information about status of the validation process for the [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md).

### Package Validation Attributes

* **id** - the numeric package validation ID
* **status** - the status of the validation process. Possible values for this field are:
  * **running**
  * **completed**
  * **failed**
* **status_message** - information about current status
* **runtime** - current duration of the validation process
* **package_id** - the numeric package ID
* **owner_id** - the numeric user ID of the package validation owner
* **account_id** - the numeric ID of the account, where package is assigned
* **errors** - the list of the errors which were detected in the validation process
* **created_at** - the date and time the validation was started
* **updated_at** - the date and time the validation status was last updated
* **url** - the package validation resource URL
