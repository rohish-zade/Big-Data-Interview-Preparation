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