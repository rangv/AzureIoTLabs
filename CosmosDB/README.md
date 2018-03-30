![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/cosmosdb.jpg "Header Image")
# Create Cosmosdb and Store Data

#### Learn how to set up a CosmosDB and Store Time Series Data

#### Azure Cosmos DB is Microsoft's globally distributed, multi-model database. The atom-record-sequence (ARS) based data model that Azure Cosmos DB is built on natively supports multiple data models, including but not limited to document, graph, key-value, table, and column-family data models

#### Elastically and independently scale throughput and storage on demand and worldwide

#### Azure Cosmos DB provides five consistency levels: strong, bounded-staleness, session, consistent prefix, and eventual. 


## Create Cosmos DB Account

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/01_Create_CosmosDB.png "Create Cosmos DB")

####

## Pick an API. For this tutorial we will use SQL API. Available APIs are

####

1. SQL API: A schema-less JSON database engine with rich SQL querying capabilities.
2. MongoDB API: A massively scalable MongoDB-as-a-Service powered by Azure Cosmos DB platform. Compatible with existing MongoDB libraries, drivers, tools, and applications.
3. Cassandra API: A globally distributed Cassandra-as-a-Service powered by Azure Cosmos DB platform. Compatible with existing Apache Cassandra libraries, drivers, tools, and applications.
4. Graph (Gremlin) API: A fully managed, horizontally scalable graph database service that makes it easy to build and run applications that work with highly connected datasets supporting Open Graph APIs (based on the Apache TinkerPop specification, Apache Gremlin).
5. Table API: A key-value database service built to provide premium capabilities (for example, automatic indexing, guaranteed low latency, global distribution) to existing Azure Table storage applications without making any app changes

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/02_Create_CosmosDB_Submit.png "Create Cosmos DB")

####


## Stop Stream Analytics

####

#### To Add Cosmos DB as output to Stream Analytics Job you will need to Stop the job, Add Cosmos DB output and corresponding Query and Start the job

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/03_stop_stream_analytics_job.png "Stop Stream Analytics Job")

####


## Stream Data To Cosmos DB

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/04_click_output.png "Stream Data to Cosmos DB")

####

#### Add Cosmos DB as an Output to Stream Analytics Job

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/05_add_cosmosdb.png "Stream Data to Cosmos DB")

####

#### Select Cosmos DB as an output. Also make sure you create a new Database and a collection if its is not already created

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/06_create_output.png "Select Cosmos DB Account")

####

#### Edit existing query to Add new query to consume data from IoTHub and store data into Cosmos DB 

####

```sql
SELECT
    *, System.Timestamp as time
INTO
    CosmosDB
FROM
    IotHub
GROUP BY deviceId, TumblingWindow(second,30)
```

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/07_Edit_Query.png "Edit Query")

####

#### Start Stream Analytics Job

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/08_start_asa.png "Start Stream Analytics Job")

####

#### Make sure you stream all the data from when you last stopped the job. Stream Analytics interface provides an option

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/09_when_last_stopped.png "Stream Data to Cosmos DB")

####

#### Make sure Stream Analytics job goes into running mode

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/10_running.png "Stream Data to Cosmos DB")

####

#### Use Cosmos DB data explorer to view data being streamed from IoTHub to Cosmos DB

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/CosmosDB/images/11_cosmosdb_data_explorer.png "Stream Data to Cosmos DB")

####
