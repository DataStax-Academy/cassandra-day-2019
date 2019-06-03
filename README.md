Welcome to Cassandra Day
========================================

In this repository, you'll find everything from the Cassandra Day event. There are materials used during presentations, hands-on exercises and reference applications. Feel free to bookmark this page for future reference!

<img src="./img/CassandraDayBanner.png" height="200" />

## Agenda

| Time  | Title
|---|---|
| 10:30 AM - 12:00 PM  | [Core Cassandra](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/slides/Cassandra%20Day%20-%20Core%20Cassandra.pdf)  |
| 12:30 PM - 02:30 PM | [Cassandra Data Modeling](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/slides/Cassandra%20Day%20-%20Data%20Modeling.pdf)  |
| 02:45 PM - 04:00 PM | [Cassandra Application Development](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/slides/Cassandra%20Day%20-%20Application%20Development.pdf)  |

## Hands-On Exercises

#### Instructions
* [Install DataStax Enterprise](https://docs.datastax.com/en/install/doc/install60/installTOC.html)

Or use Docker :
```
docker run -e "DS_LICENSE=accept" -it -d -p 9042:9042 --name dse datastax/dse-server -s -g
```

* [Install DataStax Studio](https://docs.datastax.com/en/install/doc/install60/installStudio.html)
   - The notebooks below should be [imported](https://docs.datastax.com/en/studio/6.0/studio/importNotebook.html) and opened in DataStax Studio

Or use Docker :
```
docker run -e "DS_LICENSE=accept" -it -d -p 9091:9091 --link dse:dse datastax/dse-studio
```

_If you are using docker DSE Server you may have to change the KeyspaceDefinition with_
```
CREATE KEYSPACE IF NOT EXISTS killrvideo WITH REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : 1 };
```

#### Core Cassandra
| Notebook File | Setup Notes
|---|---|
| [Core Cassandra First Touch](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/notebooks/Core_Cassandra_First_Touch.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/cassandra-day-2019/tree/master/setup/load-data) in the `killrvideo` keyspace.
| [Core Cassandra Data Loading](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/notebooks/Core_Cassandra_Data_Loading_DataStax_Cassandra_Day.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/cassandra-day-2019/tree/master/setup/load-data) in the `killrvideo` keyspace.<br> - Uses the file **movies.csv**, located in this repo under `data/csv/movies.csv`.
| [Core Cassandra Data Availability](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/notebooks/Core_Cassandra_Data_Availability_DataStax_Cassandra_Day.studio-nb.tar) | - This notebook exercise can only be done with a three-node DSE cluster.<br> - Recommended to drop the `killrvideo` keyspace, if it exists.<br>- Uses a hard-coded datacenter `DC1`; replace that with your own datacenter name, where needed.<br> - Install and setup [DataStax OpsCenter](https://docs.datastax.com/en/install/doc/install60/opscInstallOpsc.html) to monitor your cluster.

#### Data Modeling
| Notebook File | Setup Notes
|---|---|
| [Intro](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/notebooks/Data_Modeling_Data_Modeling_Intro_DataStax_Cassandra_Day.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/cassandra-day-2019/tree/master/setup/load-data) in the `killrvideo` keyspace.
| [Cassandra-Land Project Part 1](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/notebooks/Data_Modeling_Cassandra-Land_Project_PART_1.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/cassandra-day-2019/tree/master/setup/load-data) in the `killrvideo` keyspace.
| [Cassandra-Land Project Part 2](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/notebooks/Data_Modeling_Cassandra-Land_Project_PART_2.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/cassandra-day-2019/tree/master/setup/load-data) in the `killrvideo` keyspace.
| [Cassandra-Land Project Part 3](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/notebooks/Data_Modeling_Cassandra-Land_Project_PART_3.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/cassandra-day-2019/tree/master/setup/load-data) in the `killrvideo` keyspace.

#### Application Development
| Notebook File | Setup Notes
|---|---|
| [Prepared Statements](https://github.com/DataStax-Academy/cassandra-day-2019/blob/master/notebooks/Application_Development_Prepared_Statements.studio-nb.tar) | - The [KillrVideo reference app](https://killrvideo.github.io/docs/languages/java/) should be set up using the `app-cassandra-day-exercises` branch.

### Extra Materials

* Get involved more tutorials here [DataStax Academy](https://academy.datastax.com/)
* Learn more about [KillrVideo](https://github.com/killrvideo)
* More sample codes [HERE](https://github.com/DataStaxCodeSamples)
