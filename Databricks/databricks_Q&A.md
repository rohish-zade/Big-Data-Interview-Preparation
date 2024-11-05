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
- There are two types of compute planes depending on the compute that you are using.
  - For serverless compute, the serverless compute resources run in a serverless compute plane in your client Databricks account.
  - For classic client Databricks compute, the compute resources are in your client subscription in what is called the classic compute plane. This refers to the network in your client subscription and its resources.
- Each Azure Databricks workspace has an associated storage account known as the workspace storage account. The workspace storage account is in your Azure subscription.

  ![](https://github.com/rohish-zade/Big-Data-Interview-Preparation/blob/main/images/databricks_architecture.png)