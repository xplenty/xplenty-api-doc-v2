##Xplenty

[Xplenty](http://www.xplenty.com) is a data integration service that harnesses the power of [Hadoop](http://hadoop.apache.org) to provide an easy-to-use, scalable [ETL](http://en.wikipedia.org/wiki/Extract,_transform,_load) service that makes it a snap to prepare your structured and semi-structured data for analytics.

With [Xplenty](http://www.xplenty.com), you can process data generated from Heroku apps. [Xplenty](http://www.xplenty.com) can join data from multiple sources, including MySQL, PostgreSQL and MongoDB, and provides a wide range of out-of-the-box data transformation tasks, from simple sorting and aggregation to sophisticated functions and data manipulations.

When finished, place your transformed data in analytics stores such as [AWS Redshift](https://aws.amazon.com/redshift), [SAP HANA](https://aws.amazon.com/sap/saphana), or back in your favorite relational database, cloud storage or NoSQL data store.


##Installing the add-on
Xplenty can be installed to a Heroku application via the CLI:


```term
$ heroku heroku addons:add xplenty
```
## Integration


Once you've completed the previous section you're all set to use the xplenty interface.



## Xplenty interface

The interface can be accessed via the CLI.

```term
$ heroku addons:open xplenty
```

##Understanding Xplenty Terminology

###Package
An Xplenty package is a data flow definition. It describes the data to process (location, schema, fields), data manipulation to perform, and the output destinations (location, schema). Once the package is defined, it is run as a job on a cluster.

###Cluster
An Xplenty cluster is a Hadoop cluster - a group of machines (nodes) that that is allocated exclusively to your account's users. You can create one or more clusters, and you can run one or more jobs on each cluster. A cluster that you've created remains allocated to your account until you request to terminate the cluster.

###Job
An Xplenty job is a process that is responsible for running a specific package on a Hadoop cluster. The job is a batch process that processes a finite amount of data and then terminates. Several jobs can run the same package simultaneously. When you run a new job, you select the name of the package whose workflow the job should perform, and the cluster on which to run.

##Defining Connections
You can define connections that contain access information required to connect to your various data stores. The access information is stored securely and can only be used by your account's members. 

You can define two types of connections:

1) [cloud storage connection](http://community.xplenty.com/knowledgebase/articles/170932)

2) [database connection](http://community.xplenty.com/knowledgebase/articles/204166)


## Migrating between plans


Use the `heroku addons:upgrade` command to migrate to a new plan.

```term
$ heroku addons:upgrade xplenty:newplan
```

## Removing the add-on

Xplenty can be removed via the  CLI.

> Warning:
>  This will remove your xplenty connection and cannot be undone!

```term
$ heroku addons:remove xplenty
```

## Support

All xplenty support and runtime issues should be submitted via one of the [Heroku Support channels](https://support.heroku.com). Any non-support related issues or product feedback is welcome at [xplenty customer feedback](https://xplenty.uservoice.com).

## Additional resources
* [Xplenty website](https://www.xplenty.com)
* [Xplenty documentation](http://community.xplenty.com/knowledgebase/)
* [Xplenty sandbox account](https://www.xplenty.com/signup/)
