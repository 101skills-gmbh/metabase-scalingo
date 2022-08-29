# Metabase

## Deploying Metabase to Scalingo

Based on [https://github.com/Scalingo/metabase-scalingo](https://github.com/Scalingo/metabase-scalingo).

## Configuring the Application Deployment Environment

The following environment variables are available for you to adjust, depending
on your needs:

| Name                 | Description                                                                              | Default value                                   |
| -------------------- | ---------------------------------------------------------------------------------------- | ----------------------------------------------- |
| `BUILDPACK_URL`      | URL of the buildpack to use.                                                             | https://github.com/Scalingo/multi-buildpack.git |
| `DATABASE_URL`       | URL of your database addon. **Only available if you have a database addon provisioned**. | Provided by Scalingo                            |
| `MAX_METASPACE_SIZE` | Maximum amount of memory allocated to Java Metaspace[^1].                                | `512m` (512MB)                                  |

Metabase also [supports many environment variables](https://www.metabase.com/docs/latest/operations-guide/environment-variables.html).

[^1]: See https://wiki.openjdk.org/display/HotSpot/Metaspace for further details about Java Metaspace.

## Updating Metabase on Scalingo

To upgrade to the latest version of Metabase, you only need to redeploy it,
this will retrieve the latest version avaible on [the Metabase buildpack](https://github.com/metabase/metabase-buildpack).

## Updating After Deploying Using Scalingo's Command Line Tool

```bash
$ cd metabase-scalingo
$ git pull origin master
$ git push scalingo master
```
