An Xplenty **job** is a process that is responsible for performing a data flow according to a specific package on a cluster. The job is a batch process that runs on a finite amount of data and then terminates. Several jobs can run the same package simultaneously.
When you call the Xplenty API to run a new job, you supply the name of the package whose workflow the job should perform, and the cluster on which to run.

### Job Attributes

* **id** - the numeric job ID
* **status** - the job status. Possible values are: 
  * **idle** - the user sent a request to run the job
  * **pending** - the job is initializing
  * **queued** - the job is waiting for cluster resources
  * **running** - the job is running
  * **completed** - the job completed successfully
  * **failed** - the job failed to complete
  * **pending_stoppage** - the user sent a request to stop the job
  * **stopping** - the job is stopping
  * **stopped** - the job has stopped
* **variables** - a list of the variables supplied to the "run" request
* **master_auto_retry_attempts** - the total automatic retry attempts configured by the schedule for this job; null if the job was not created by a schedule or if auto-retry is disabled.
* **attempts** - the number of retry attempts already performed by the schedule for this job; 0 for the initial (non-retry) run, and 1, 2, ... for subsequent retries.
* **owner_id** - the numeric user ID
* **progress** - the job progress in percentages (a value between 0.0 and 1.0)
* **outputs_count** - the number of output targets defined in the job's package
* **outputs** -  list of the output targets defined in the job's package
  * **id** - the numeric job output ID
  * **name** -  the job output name (filename, link, etc)
  * **records_count** - the number of records in this output
  * **progress** - the progress of storing job output
  * **created_at** - the date and time the store of this output started
  * **updated_at** - the date and time this job output was last updated
  * **preview_url** - the job output preview resource URL
  * **preview_type** - the type of the preview e.g. json, csv etc
  * **url** - the job output resource URL
  * **component** - the component for which this output was created
    * **name** - the name of the component
    * **type** - the type of the component
    * **fields** - the fields of the component
* **started_at** - the date and time the job started running
* **created_at** - the date and time the "run" request was made
* **failed_at** - the date and time the job failed (if it failed)
* **updated_at** - the date and time the job was last updated (occurs when package tasks are completed)
* **cluster_id** - the ID of the cluster in which the job was run
* **cluster** - the [cluster](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/cluster.md) in which the job was run. Includes all attributes.
* **package_id** - the ID of the package that the job ran (or is running)
* **package** - the [package](https://github.com/xplenty/xplenty-api-doc-v2/blob/master/resources/package.md) that the job ran (or is running). Includes all attributes.
* **errors** - a textual message describing errors encountered while the job was run
* **runtime_in_seconds** - the time in seconds that the job has run up to the current time
* **completed_at** - the date and time at which the job completed (stopped, failed or completed)
* **url** - the job resource URL (API)
* **html_url** - the job resource URL (Web UI)
* **creator** - information about resource which created the job. It contains the following values:
  * **type** - the type of the resource (e.g. Schedule)
  * **id** - the numeric resource ID
* **component** - the component for which this output was created
  * **name** - the name of the component
  * **type** - the type of the component
* **log_url** - the URL to log summary
