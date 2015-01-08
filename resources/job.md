An Xplenty **job** is a process that is responsible for performing a data flow according to a specific package on a Hadoop cluster. The job is a batch process that runs on a finite amount of data and then terminates. Several jobs can run the same package simultaneously.
When you call the Xplenty API to run a new job, you supply the name of the package whose workflow the job should perform, and the cluster on which to run.

### Job Attributes

* **id** - the numeric job ID
* **status** - the job status. Possible values are: 
  * **idle** - the user sent a request to run the job
  * **pending** - the job is initializing
  * **running** - the job is running
  * **completed** - the job completed successfully
  * **failed** - the job failed to complete
  * **pending_stoppage** - the user sent a request to stop the job
  * **stopping** - the job is stopping
  * **stopped** - the job has stopped
* **variables** - a list of the variables supplied to the "run" request
* **owner_id** - the numeric user ID
* **progress** - the job progress in percentages (a value between 0.0 and 1.0)
* **outputs_count** - the number of output targets defined in the job's package
* **outputs** -  list of the output targets defined in the job's package
* **started_at** - the date and time the job started running
* **created_at** - the date and time the "run" request was made
* **failed_at** - the date and time the job failed (if it failed)
* **updated_at** - the date and time the job was last updated (occurs when package tasks are completed)
* **cluster_id** - the ID of the cluster in which the job was run
* **package_id** - the ID of the package that the job ran (or is running)
* **errors** - a textual message describing errors encountered while the job was run
* **url** - the job resource URL
* **runtime_in_seconds** - the time in seconds that the job has run up to the current time
* **completed_at** - the date and time at which the job completed (stopped, failed or completed)
