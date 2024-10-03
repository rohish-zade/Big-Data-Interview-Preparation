# What is Apache Hive?

Apache Hive is a data warehousing service and SQL-like query language (HiveQL) built on top of Hadoop.
It enables users to analyze and query large datasets stored in Hadoop’s HDFS using a SQL-like interface.
Hive simplifies the process of querying and managing large datasets without requiring in-depth knowledge of Java or MapReduce.
It converts HQL query into Map-Reduce code.


## Key Features of Hive:
- SQL-like Interface: HiveQL (Hive Query Language) is similar to SQL.
- Data Warehousing: Allows users to store and query structured data.
- Scalability: Designed to work with large datasets stored in HDFS.
- Batch Processing: It is optimized for batch processing rather than real-time analytics.
- Schema on Read: Data is interpreted at query time, not when it is loaded into Hive.


## Apache Hive Architecture

The architecture of Apache Hive is designed to process and manage large datasets stored in Hadoop's HDFS using SQL-like queries
![](https://github.com/rohish-zade/Big-Data-Interview-Preparation/blob/main/images/schemat-hive-1.png)


### Hive Client:
- Hive drivers support applications written in any language like Python, Java, C++, and Ruby, among others, using JDBC, ODBC, and Thrift drivers, to perform queries on the Hive. Therefore, one may design a hive client in any language of their choice.
- The three types of Hive clients are referred to as Hive clients:
  - `Thrift Clients`: The Hive server can handle requests from a thrift client by using Apache Thrift.
  - `JDBC client`: A JDBC driver connects to Hive using the Thrift framework. Hive Server communicates with the Java applications using the JDBC driver.
  - `ODBC client`: The Hive ODBC driver is similar to the JDBC driver in that it uses Thrift to connect to Hive. However, the ODBC driver uses the Hive Server to communicate with it instead of the Hive Server.


### Hive Services:
Hive provides numerous services, including the Hive server2, Beeline, etc. The services offered by Hive are:
- `Beeline`: HiveServer2 supports the Beeline, a command shell that which the user can submit commands and queries to. It is a JDBC client that utilises SQLLINE CLI (a pure Java console utility for connecting with relational databases and executing SQL queries). The Beeline is based on JDBC.
- `Hive Server 2`: HiveServer2 is the successor to HiveServer1. It provides clients with the ability to execute queries against the Hive. Multiple clients may submit queries to Hive and obtain the desired results. Open API clients such as JDBC and ODBC are supported by HiveServer2.

**Note**: Hive server1, which is also known as a Thrift server, is used to communicate with Hive across platforms. Different client applications can submit requests to Hive and receive the results using this server.

HiveServer2 handled concurrent requests from more than one client, so it was replaced by HiveServer1.


### Hive Driver:
The Hive driver receives the HiveQL statements submitted by the user through the command shell and creates session handles for the query sends the query to the compiler.


### Hive Compiler:
- The compiler compiles HiveQL queries into execution plans. 
- It translates the queries into MapReduce or Tez jobs based on the engine used.
- The compiler interacts with the Metastore to get schema information and optimizes the execution plan before submitting it for execution.
- The DAG (Directed Acyclic Graph) is a DAG structure created by the compiler. Each step is a map/reduce job on HDFS, an operation on file metadata, and a data manipulation step.


### Optimizer: 
The optimizer splits the execution plan before performing the transformation operations so that efficiency and scalability are improved.


### Execution Engine: 
After the compilation and optimization steps, the execution engine uses Hadoop to execute the prepared execution plan, which is dependent on the compiler’s execution plan.


### Metastore:
- Metastore stores metadata information about tables and partitions, including column and column type information, in order to improve search engine indexing.
- The Metastore serves as the central repository for all schema and structural information related to Hive tables.
- The metastore also stores information about the serializer and deserializer as well as HDFS files where data is stored and provides data storage.


### Processing and Resource Management:
- Hive uses a MapReduce framework as a default engine for performing the queries, because of that fact.
- MapReduce frameworks are used to write large-scale applications that process a huge quantity of data in parallel on large clusters of commodity hardware. MapReduce tasks can split data into chunks, which are processed by map-reduce jobs.


### Distributed Storage:
Hive is based on Hadoop, which means that it uses the Hadoop Distributed File System(HDFS) for distributed storage.


### Working with Hive:



