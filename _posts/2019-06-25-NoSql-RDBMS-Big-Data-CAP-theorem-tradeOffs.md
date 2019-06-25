
Before getting into the details of CAP theorem and positioning of RDBMS and NOSQL , let's briefly talk on CAP stands off.

**C- Consistency** .   All clients will have always have the same view of data. All the servers in the system will have the same data so anyone using the system will get the same copy regardless of which server answers their request.

**A- Availability**. Each Client can always Read & Write.  The system will always respond to a request (even if it's not the latest data or consistent across the system or just a message saying the system isn't working)

**P - Partitioning**  . System works despites physical network partitioning . The system continues to operate as a whole even if individual servers fail or can't be reached.

Current  Data Models available in the market.

 - **RDBMS** - Relational DataBase Management System - MySQL, Oracle, MariaDB
 - **Key Value**  - Redis DB
 - **Column Oriented /Tabular** -  Cassendra, HBase
 - **Document Oriented** -MongoDB ,CouchDB

Let's get into the deep dive by questioning the data sizes and Simultaneous Read/Writes .

How do you handle the volumes of data upto 20GB and high TPS Read/Write(Throughput per sec) ?  Any RDBMS - single master will be enough to handle the requests. MySQL, Oracle, AWS RDS can suffice your needs

How do you handle the volumes of data between 20GB to 150GB and high TPS (Throughput per sec) ? Partitioned base Master and Sharded volumes can support . Example, MongoDB.  I got your question, how can the master db will  make sure if one shard is not connected ? It works read mode if any sharded volumen is down, atleast it will not have any dataloss/ inconsistency.  It is still a good tradeoff to manage the smaller volumes instead of big volume. Rethink DB is also a good competitor on this regard.

Here are the few analysis done on  DB's which are available in the market

**CouchDB**  :  **AP**  ( Availability & Partition) & Document database
**Cassandra**  :  **AP**  ( Availability & Partition) & Column family database
**MongoDB**  :  **CP**  ( Consistency & Partition) & Document database
**MySQL**  :  **CA**  ( Consistency & Availability) & Document database

**MongoDB - Tradeoff's when Partitions are CONNECTED or NOT CONNECTED** .
```
Scenario                   | Main Focus | Description
    ---------------------------|------------|------------------------------------
    No partition               |     CA     | The system is available 
                               |            | and provides strong consistency
    ---------------------------|------------|------------------------------------
    partition,                 |     AP     | Not synchronized writes 
    majority connected         |            | from the old primary are ignored                
    ---------------------------|------------|------------------------------------
    partition,                 |     CP     | only read access is provided
    majority not connected     |            | to avoid separated and inconsistent systems
```

MYSQL - trade offs : By default the MYSQL installation comes with CA .  Master Slave paradigm  takes care of writing the data to the slaves.  By changing the MYSQL configuration with cluster enablement , it prioritizes CP over the CA . Example:  the cluster will shutdown if there are not enough live nodes to serve all the data.
Every DB which is coming up in the market wants to achieve all the three challenges of CAP theorem.  It has to take tradeoff for atleast one item while achieving the goal.

One of the good db in the market which achieved rare feat by having proper tradeoff's is RethinkDB . By the core, it was able to do with reactive based approach and full support for Push kind of needs. eg: Whatsapp requires the push kind of needs for alerting to the members & groups . Like 1:1 , 1: Many needs.
You can go through the architecture below.
[https://rethinkdb.com/docs/architecture/](https://rethinkdb.com/docs/architecture/)
