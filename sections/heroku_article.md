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
