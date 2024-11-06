## Basics of Databricks and Azure Data Engineering

### 1. What is Databricks?

Databricks is a unified, open analytics platform for building, deploying, sharing, and maintaining enterprise-grade data, analytics, and AI solutions at scale. The Databricks Data Intelligence Platform integrates with cloud storage and security in your cloud account, and manages and deploys cloud infrastructure on your behalf.

- Databricks is a unified data analytics platform built to work with big data and machine learning applications. 
- It was developed by the creators of Apache Spark and provides an integrated environment for processing large-scale data with support for both structured and unstructured data.
- Databricks offers cloud-based infrastructure (primarily on Azure, AWS, and Google Cloud) and simplifies big data workflows with an emphasis on collaborative data engineering, data science, and machine learning.
- Databricks provides a collaborative environment for data engineers, data scientists, and business analysts to work together on data projects.


### 2. What is Databricks used for?

Databricks is a versatile platform used across industries for `big data processing`, `analytics`, and` machine learning`. Here are some common use cases for Databricks:

- Data Engineering: Building scalable ETL pipelines.
- Data Warehousing and BI: Querying and visualizing data for business insights.
- Real-Time Analytics: Processing streaming data for immediate insights.
- Machine Learning: Training and deploying models at scale.
- Advanced Analytics: Conducting data science and statistical analysis.
- Lakehouse Architecture: Combining data lake and warehouse features.
- Scientific Research: Analyzing large datasets for research applications.

### 3. Databricks Architecture (Data Plane and Control Plane)

Databricks operates out of a control plane and a compute plane.

**Control Plane:**
- It is located in the Databricks account which contains backend services managed by Databricks.
- `User Interface:` Hosts the Databricks web application, where users access the Databricks Workspace, create notebooks, manage clusters, and monitor jobs.
- `Job Scheduling and Management:` Manages job scheduling and orchestration, ensuring that jobs are triggered on the compute plane as per configuration.
- `Cluster Management:` Manages the lifecycle of clusters, including creation, auto-scaling, and termination, but it does not handle the actual data processing tasks.
- `Metadata and Authentication:` Manages metadata (e.g., notebook contents, cluster configurations) and handles user authentication, role-based access control (RBAC), and permissions for secure access to resources.
- The Control Plane does not access or process customer data directly; instead, it manages the environment and resources that do.

**Compute Plane:**
- The compute plane is where your data is processed.
- The Compute Plane is where actual data processing and analytics tasks occur. This plane hosts all the clusters and resources that execute code and process data.
- Unlike the Control Plane, the Compute Plane is typically hosted in the customer’s cloud account, ensuring that data remains within their control and security parameters.


- There are two types of compute planes depending on the compute that you are using.
  - For serverless compute, the serverless compute resources run in a serverless compute plane in your client Databricks account.
  - For classic client Databricks compute, the compute resources are in your client subscription in what is called the classic compute plane. This refers to the network in your client subscription and its resources.
- Each Azure Databricks workspace has an associated storage account known as the workspace storage account. The workspace storage account is in your Azure subscription.

  ![](https://github.com/rohish-zade/Big-Data-Interview-Preparation/blob/main/images/databricks_architecture.png)


**How Control and Compute Planes Interact:**
- The Control Plane instructs the Compute Plane to initiate clusters, schedule jobs, and manage resource scaling, but it does not perform actual computations.
- When a user initiates a job or query, the Control Plane sends commands to the Compute Plane, which then executes the job on the cluster.
- Cluster configurations, job metadata, and other management instructions are handled by the Control Plane, while the Compute Plane focuses on data processing.


### 4. Cluster/Compute in Databricks
A cluster in Databricks is a set of computation resources and configurations that you use to run your notebooks, jobs, or any other computation tasks. It consists of a driver node and one or more worker nodes.

- Driver coordinates activities of executors.
- Executors run tasks composing a Spark job.

### 5. Types of Clusters
In Databricks, there are primarily three types of clusters, each serving different purposes based on your workflow needs. Here’s a detailed overview of each cluster type:

**Standard Clusters:**
- Designed for general-purpose tasks, Standard clusters support both interactive and scheduled workloads. 
- They can be started manually or auto-scaled, providing a persistent environment for running notebooks and jobs.

**All-Purpose Clusters**
- All-Purpose clusters enable interactive data analysis and collaborative development.
- They allow multiple users to work on notebooks simultaneously, making them ideal for exploratory data science and analytics workflows.

**Job Clusters:**
- Job clusters are Specifically created for running scheduled jobs or automated tasks.
- They terminate automatically after the job completes, optimizing resource usage and reducing costs.
- Best for executing batch jobs or scheduled workflows that don't require an interactive workspace.


### 6. What is DBU?
- When we use Databricks to run our ETL pipelines or train ML models, we consume computation power that gets measured by a Databricks Unit (or DBU for short).
- A DBU (Databricks Unit) is a unit of processing capability per hour used to measure and bill for computational resources in Databricks.
- It represents the processing power consumed by running workloads on Databricks clusters.- DBUs are calculated based on factors like cluster type, instance type, and workload, and they are a core component in Databricks’ pricing model.


### 7. Databricks Deployment

We can deploy the databricks mainly in 3 clouds that is Azure, AWS and GCP.
- Azure databrikcs is a Paas.
- AWS databricks is Saas.
- GCP Databricks: PaaS


### 8. What is DBFS?
- DBFS, or Databricks File System, is a distributed file system that comes built into Databricks.
- It allows users to store, access, and manage files and data within the Databricks environment, acting as an abstraction layer over the underlying cloud storage (such as Azure Data Lake Storage, AWS S3, or Google Cloud Storage).


### 9. What is Repos in databricks?
- Databricks Repos is a feature in Databricks that provides `Git integration` directly within the Databricks workspace.
- t enables users to version control notebooks, Python scripts, and other code files by connecting with Git repositories (like `GitHub`, `GitLab`, `Bitbucket`, or `Azure DevOps`), promoting collaborative development, and allowing efficient code management.

### 10. What is Delta Lake in databricks?
- Delta Lake is an `open-source storage layer` provided by Databricks, built on top of Apache Spark.
- It enables reliable data lakes by adding ACID (Atomicity, Consistency, Isolation, Durability) transactions, data versioning, and schema enforcement to data lakes.
- Delta Lake in Databricks is an open-source storage layer that brings `ACID` (Atomicity, Consistency, Isolation, Durability) `transactions`, `data versioning`, and `schema enforcement` to data lakes, solving many of the common challenges associated with traditional data lakes.

### 11. What is Data Lakehouse in databricks?
- A Data Lakehouse in Databricks is an architectural approach that combines the best features of `data lakes` and `data warehouses`.
- The lakehouse model allows organizations to manage and analyze vast amounts of structured and unstructured data in a single platform, bridging the gap between `analytics` and `big data processing`.
- Featues or benefits of lakehouse:
  - `Unified Data Storage:` Data lakehouses store both raw (unstructured) and processed (structured and semi-structured) data in a single repository, often using cloud-based storage like Azure Data Lake Storage (ADLS) in Databricks.
  - `Support for Multiple Workloads:` Databricks Lakehouse allows different types of data processing on a single platform, from ETL (Extract, Transform, Load) and batch processing to streaming and interactive analytics
  - `Delta Lake Format: `The Delta Lake technology, integral to Databricks, enables ACID (Atomicity, Consistency, Isolation, Durability) transactions, schema enforcement, and version control.
  - `Built-in Security and Governance:` Databricks integrates with tools to ensure data security, compliance, and governance, providing fine-grained access control, data lineage, and auditability.
  - `Performance Optimizations:`The lakehouse architecture includes high-performance query optimization techniques, like caching, indexing, and Z-Ordering, to speed up queries on large datasets.
  - `Support for BI, Data Science, and ML Workloads`:Unlike traditional data lakes, the lakehouse model supports diverse use cases, from business intelligence (BI) reporting to data science and machine learning workflows. 


### 12. What are the features of delta table?
Delta Tables are a core component of Delta Lake in Databricks and bring various features that enhance the `reliability`, `performance`, and `manageability` of data in a data lake environment.
- `ACID Transactions`: Ensures data reliability by supporting atomic, consistent, isolated, and durable operations.
- `Time Travel (Data Versioning)`: Allows querying and reverting to historical data versions at any point in time.
- S`chema Enforcement:` Enforces a schema to prevent corrupt or inconsistent data from being written to the table.
- `Schema Evolution:` Supports automatic schema changes (e.g., adding new columns) without affecting existing data.
- `Upserts, Deletes, and Merges:` Enables efficient updates, deletions, and upserts for handling slowly changing dimensions.
- `Data Skipping and Z-Ordering:` Optimizes query performance by skipping irrelevant data and sorting for efficient data access.
-` Unified Batch and Streaming Support`: Allows seamless integration of batch and real-time streaming data in the same table.
- `Built-In Data Quality Features:` 
  - Delta Tables offer vacuuming to remove old data files that are no longer needed, as well as support for data compaction and `OPTIMIZE` commands to reduce storage and improve read performance.
  - These maintenance features allow me to manage storage efficiently and ensure data quality without excessive manual intervention, particularly useful in production environments where performance is critical.


### 13. What is VACUUM  and OPTIMIZE  command in databricks?
In Databricks, the `VACUUM` and `OPTIMIZE` commands are used for maintaining and optimizing Delta Tables to improve performance and manage storage effectively.

**VACUUM Command:**
- The `VACUUM` command is used to remove old, outdated data files from a Delta Table. This helps reclaim storage space and ensure the table doesn’t accumulate unnecessary files that could impact performance.

Key Points:
- Delta Lake supports time travel, which allows querying historical versions of data. However, as data evolves, older versions of data may not be needed and can be safely removed.
- Default retention period: The VACUUM command removes files older than a specified retention period (by default, 7 days), which helps ensure that the Delta Table remains lean and efficient.
- The command is necessary after deleting or updating records, as Delta Lake doesn't immediately remove old versions of files to support time travel queries.
- Syntax:
  ```sql
  VACUUM <table_name> [RETAIN <hours> HOURS]

  -- Example: By default, VACUUM removes data older than 7 days, but you can override this by specifying a custom retention period (in hours).
  VACUUM delta.`/path/to/table` RETAIN 168 HOURS;
  ```

**OPTIMIZE Command:**
The `OPTIMIZE` command is used to improve the performance of queries on a Delta Table by compacting small files into larger ones and organizing the data files for efficient reads.

Key Points:
- Delta Tables can generate many small files over time, especially in scenarios involving frequent writes or streaming data. These small files can significantly impact query performance, as reading many small files is slower than reading a few large files.
- Z-Ordering: The OPTIMIZE command can also include Z-Ordering, which reorders the data within the table based on specified columns to improve query performance for certain types of filters. It helps by reducing the amount of data scanned during queries.
- Syntax:
  ```sql
  OPTIMIZE <table_name> [WHERE <condition>] [ZORDER BY <col1>, <col2>, ...]
  ```
  - The `ZORDER BY` clause is optional and helps optimize the performance for queries that filter on specific columns.
  - The `WHERE` clause allows you to optimize a subset of the table, based on a condition.
- Example:
  ```sql
  OPTIMIZE my_table ZORDER BY (date, user_id)
  ```

**Key Differences:**
- `VACUUM`: Cleans up old and unnecessary files to free up storage space.
- `OPTIMIZE`: Combines small files into larger ones for improved performance, especially for queries that involve specific columns.

### 14. What is delta_log in delta table?
- In Delta Lake, the `delta_log` (also known as the transaction log) is a critical component that tracks all changes made to a Delta Table.
- It resides in a folder named `_delta_log` within the Delta Table's directory and stores information about every transaction, including metadata and operations like inserts, updates, deletes, and schema changes.
- Inside the _delta_log folder of a Delta table, you will find the following types of files:
  - `JSON files:` 
    - These files contain the transaction log entries that record changes to the Delta table. Each JSON file represents a single transaction (write operation). They include details like: 
      - The type of operation (e.g., addFile, removeFile, metaData, txnCommit)
      - File paths, partition information, and data file metadata
      - Timestamps and version numbers of the transaction
    - he files are named sequentially as 00000000000000000001.json, 00000000000000000002.json, and so on.
  - `Checkpoint files` (_delta_log/*.checkpoint.parquet):
    - These are Parquet files that contain a snapshot of the state of the Delta table at a particular point in time.
    - Checkpoints are created periodically to optimize reading the transaction log and avoid reading all the JSON log files for every query. 
    - A checkpoint file contains the entire transaction history up to that point, stored in a more compact and efficient format (Parquet).
    - for every 10 json transaction files one checkpoint file will be created.
  - `CRC file` (Cyclic Redundancy Check file)
    - CRC files are used to store checksums for the corresponding JSON or checkpoint files in the Delta log. 
    - They help in validating that the log files have not been corrupted and can be read correctly.
    - When Delta Lake reads the transaction log files, it verifies the integrity of the log files by comparing the checksums stored in the .crc files with the actual content of the log files.


### 14. What is Multi-hop/Medallion Architecture?
The Multi-hop (or Medallion) Architecture is a design pattern for building scalable, maintainable, and efficient data pipelines in a data lakehouse environment, typically using tools like Databricks. 

This architecture separates data processing into multiple stages or layers, often referred to as bronze, silver, and gold layers, each serving a specific purpose.
 
  ![](https://github.com/rohish-zade/Big-Data-Interview-Preparation/blob/main/images/building-data-pipelines-with-delta-lake-120823.png)

**Bronze Layer (Raw Data):**
- This layer stores raw, untransformed data ingested directly from source systems (e.g., raw logs, transactional data, IoT data). It is typically stored in its most granular form without much processing.
- Typically just a raw copy of ingested data.
- This layer serves as a durable, source-of-truth repository.
- It may contain errors, duplicates, or incomplete data. This layer is used primarily for storage and later processing.

**Silver Layer (Cleaned or Transformed Data):**
- This layer contains data that has undergone cleansing and transformation. 
- The raw data from the bronze layer is cleaned, enriched, and integrated to make it more useful for analysis.
- Data is typically aggregated or enriched for analysis.
- Serves as a reliable source for reporting or machine learning applications
- Data transformation, data enrichment, filtering, and joining datasets to create a more refined, intermediate form of data for downstream analysis.
- Eliminates duplicate records

**Gold Layer (Aggregated or Business-Level Data):**
- The gold layer contains data that is ready for business intelligence (BI) or analytical purposes. 
- This data is often `aggregated`, `summarized`, or `structured` in a way that directly supports decision-making and reporting.

**Benefits of Multi-Hop Architecture:**
- `Scalability`: The architecture allows for handling large datasets efficiently by breaking down the processing into smaller, manageable stages.
- `Data Quality:` By separating raw data from processed data, data quality improves with each layer. This design also supports incremental processing and deduplication.
- `Modularity`: It allows for flexible transformations at each layer, making it easier to modify and update pipeline logic without affecting other layers.
- `Performance Optimization`: Each layer can be optimized independently for different types of workloads (e.g., batch processing for bronze, fast querying for gold).


### 14. Workflows in databricks?
In Databricks, Workflows are a set of tasks that are executed in a specified order to automate data processing, orchestration, and job management.

They allow data engineers to build and manage complex data pipelines, combining batch jobs, streaming jobs, and other automated tasks.

**Jobs in Databricks:**
- Jobs in Databricks are used to automate and schedule the execution of notebooks, Python scripts, JARs, or other code. 
- You can define the parameters and clusters to run these tasks on, enabling a repeatable, automated process for data pipelines.

**Delta Live Tables (DLT):**
- Delta Live Tables is a declarative framework for building `reliable`, `maintainable`, and `testable` data processing pipelines. 
- You define the transformations to perform on your data and Delta Live Tables manages `task orchestration`, `cluster management,` `monitoring`, `data quality`, and `error handling`.


### 15. Unity Catalog in Databricks?
Unity Catalog is a unified governance solution in Databricks that centralizes and simplifies data management across various workspaces and environments.

It provides a unified interface for managing all the data assets (`tables`, `views`, `schemas`, etc.) in Databricks and integrates with Databricks' Metastore, which is a service that manages metadata for your data.

  ![](https://github.com/rohish-zade/Big-Data-Interview-Preparation/blob/main/images/unity_catalog.png)

Key Concepts in Unity Catalog:

**Metastore:**
- The Databricks Metastore is a centralized repository that stores metadata for your data assets, such as tables, schemas, and views. 
- It enables users to discover and manage their datasets across different workspaces.

**Catalog:**
- A Catalog is a container that holds one or more databases (schemas). 
- Unity Catalog allows you to create and manage catalogs to organize your data assets.
- Example: You can create different catalogs for various business domains (e.g., “sales_catalog” and “marketing_catalog”) to logically segregate the datasets across departments.

**Database (Schema):**
- A Database (or Schema) is a logical grouping of related tables, views, and other objects.
- Further Database contains `tables`, `view` and `functions`


### 16. Widgets in Databricks
Widgets in Databricks are UI elements that allow users to parameterize notebooks, making them more interactive and versatile for different tasks or users.

Databricks widgets are best for:
- Building a notebook or dashboard that is re-executed with different parameters.
- Quickly exploring results of a single query with different parameters.

**Databricks widget types**

There are 4 types of widgets:

**Text:** 
- Input a value in a text box.
- Example: Create a text widget to manually specify a table name:
  ```python
  dbutils.widgets.text("table", "")
  ```

**Dropdown:** 
- Select a value from a list of provided values.
- Example: Create a dropdown widget of all databases in the current catalog:
  ```python
  dbutils.widgets.dropdown("database", "default", [database[0] for database in spark.catalog.listDatabases()])
  ```
**Combobox:**
- Combination of text and dropdown. Select a value from a provided list or input one in the text box.
- Example: Creating a combobox widget with default and available options
  ```python
  dbutils.widgets.combobox("country", "USA", ["USA", "Canada", "Mexico", "UK"], "Select or Enter Country")
  ```

**Multiselect:** 
- Select one or more values from a list of provided values.
- Example: Creating a multiselect widget with options
  ```python
  dbutils.widgets.multiselect("regions", "US", ["US", "EU", "APAC", "LATAM"], "Select Regions")
  ```