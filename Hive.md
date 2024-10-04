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
![](https://github.com/rohish-zade/Big-Data-Interview-Preparation/blob/main/images/Working-with-Hive-1536x1018.png)

- Query Submission: The user submits a HiveQL query through the UI (CLI, JDBC/ODBC, Web UI).
- Query Parsing: The driver parses the HiveQL query and converts it into an Abstract Syntax Tree (AST).
- Query Compilation: The query compiler converts the AST into an execution plan in the form of DAG (for MapReduce, Tez, or Spark jobs). The compiler also interacts with the Metastore to retrieve schema and data information.
- Query Optimization: The execution plan is optimized to improve performance (e.g., join reordering, partition pruning, etc.).
- Job Execution: The execution engine (MapReduce, Tez, or Spark) processes the query by executing tasks on the Hadoop cluster. The data is fetched from HDFS or another storage layer.
- Result Retrieval: Once the execution is complete, the result is returned to the user through the UI.



### Different Modes of Hive:
A hive can operate in two modes based on the number of data nodes in Hadoop.
- Local mode
- Map-reduce mode

**When using Local mode:**
- We can run Hive in pseudo mode if Hadoop is installed under pseudo mode with one data node.
- In this mode, we can have a data size of up to one machine as long as it is smaller in terms of physical size.
- Smaller data sets will be processed rapidly on local machines due to the processing speed of small data sets.

**When using Map Reduce mode:**
- In this type of setup, there are multiple data nodes, and data is distributed across different nodes. We use Hive in this scenario
- It will be able to handle large amounts of data as well as parallel queries in order to execute them in a timely fashion.
- By turning on this mode, you can increase the performance of data processing by processing large data sets with better performance.


## Types of Tables in Hive
There are two types of tables in Hive:

### 1. Managed (Internal) Table:
- Hive owns both the table schema and the data stored in the table.
- When a managed table is created, Hive stores the table data in a default location in HDFS, typically in /user/hive/warehouse/tablename/ 
- Hive is responsible for managing the data lifecycle. If you drop a managed table, both the metadata and the data in HDFS are deleted.
- Use a managed table when Hive should take full control of data management.
- Example:

   ```sql
   CREATE TABLE employee (
       id INT,
       name STRING,
       salary FLOAT
   );
   ```

### 2. External Table:
- Hive manages only the table schema (metadata), but the data itself is stored externally (outside Hive’s control).
- Data for external tables is stored at a location explicitly specified by the user (e.g., an HDFS directory or even other storage like S3).
- Dropping an external table deletes only the schema from Hive Metastore but does not delete the underlying data in HDFS.
- Use external tables when data is managed by another system or when you want to keep the data safe after dropping the table.
- Example:

   ```sql
   CREATE EXTERNAL TABLE employee_ext (
       id INT,
       name STRING,
       salary FLOAT
   )
   LOCATION '/user/external/employee_data/';
   ```


## Partitioning in Hive
Partitioning in Hive is a way to divide large tables into smaller, more manageable parts based on the values of one or more columns (known as partition keys).
Partitioning helps improve query performance by allowing Hive to scan only relevant portions of the data, instead of the entire table.


### How it Works:
- When a table is partitioned, the data is stored in separate directories in HDFS. Each directory corresponds to a specific value of the partition key (or combination of keys if there are multiple partitions).
- For example, if a table is partitioned by the "year" column, Hive will store the data in subdirectories like /year=2021/, /year=2022/, etc.
- When querying a partitioned table, Hive will only read data from the relevant partitions, reducing the amount of data scanned.

### Partitioning Levels:
- Single-Level Partitioning: Data is divided based on a single column. Example: Partitioning by "year."
- Multi-Level Partitioning: Data is divided based on multiple columns. Example: Partitioning by both "year" and "region."

### Syntax for Partitioning a Table:
- *Create a Partitioned Table:*
  ```sql
  CREATE TABLE sales (
    product_id INT,
    amount FLOAT,
    customer STRING
  )
  PARTITIONED BY (year INT, region STRING);
  ```
- In this example, the table sales is partitioned by two columns: year and region. Hive will store the data in directories such as /year=2021/region=US/.


## Advantages of Partitioning:


## Interview Questions and Answers on Hive: