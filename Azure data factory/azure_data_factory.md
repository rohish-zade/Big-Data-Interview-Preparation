# Azure Data Factory (ADF)

### 1. What is Azure Data Factory (ADF)?
- Azure Data Factory is a cloud-based ETL service that allows you to create data-driven workflows for orchestrating and automating data movement and data transformation.
- Azure Data Factory is a cloud-based data integration service to compose data storage, movement, and processing services into automated data pipelines.
- Azure Data Factory is a data ingestion and transformation service that allows you to load raw data from over 70 different on-premises or cloud sources. The ingested data can be cleaned, transformed, restructured, and loaded back into a data warehouse.


#### Common Use Cases for ADF:
- **ETL and ELT Pipelines:** Extracting data from various sources, transforming it, and loading it into data lakes or warehouses.
- **Data Migration:** Moving data between on-premises systems and cloud environments.
- **Orchestration and Automation:** Allows the scheduling and monitoring of pipelines for automated data processing.
- **Data Lake Integration:** Populating and processing data within Azure Data Lake.
- **Analytics Preparation:** Preparing and aggregating data for use in business intelligence and machine learning workflows.

#### Why Use Azure Data Factory?
Azure Data Factory simplifies the process of managing complex data workflows and eliminates the need for infrastructure management. Its flexibility, rich integrations, and scalability make it an essential tool for modern data-driven organizations.

### 2. What are the key Components in Azure Data Factory?
Azure Data Factory (ADF) consists of several key components that help in orchestrating and automating data movement and transformation. Here are the main components:

**Pipeline:** 
- A data factory might have one or more pipelines. A pipeline is a logical grouping of activities that performs a unit of work.
- For example, a pipeline can contain a group of activities that ingests data from an Azure blob, and then runs a Hive query on an HDInsight cluster to partition the data.

**Activity:**
- Activities represent a processing step in a pipeline. 
- For example, you might use a copy activity to copy data from one data store to another data store.
- Data Factory supports three types of activities: `data movement activities`, `data transformation activities`, and `control activities`.

**Linked services:**
- Linke services are used to connect other resources to with ADF.
- Linked services are much like connection strings, which define the connection information that's needed for Data Factory to connect to external resources.
- For example, an Azure Storage-linked service specifies a connection string to connect to the Azure Storage account.
- If you want to any type of resource, you need to have connection string which is linked service in ADF.

**Datasets:**
- Datasets represent data structures within the data stores, which simply point to or reference the data you want to use in your activities as inputs or outputs.
- It defines the schema and location of the data within a linked service.

**Triggers:**
- Triggers represent the unit of processing that determines when a pipeline execution needs to be kicked off.
- There are different types of triggers for different types of events.
  - `Schedule Trigger:` This type of trigger runs a pipeline based on a predefined schedule (e.g., daily, hourly, at specific intervals). 
  - `Event-based Trigger:` These triggers execute pipelines in response to specific events, such as blob storage events (e.g., new file creation or deletion).
  - `Tumbling Window Trigger:` This trigger runs pipelines at a fixed interval, suitable for working with historical data and processing data in time slices. 
- They allow you to define when and how pipelines should run based on any date time, frequency or based on some event like file creation/deletion providing flexibility in automating data workflows.

**Integration Runtime (IR)**
- Integration Runtime (IR) is the compute infrastructure used by ADF to perform data Integration activities such as data movement and transformation activities.
- It acts as the bridge between ADF and the data sources or destinations, enabling connectivity and operational execution.
- There are three types:
  - `Azure IR` – Cloud-based, managed by Microsoft.
  - `Self-hosted IR` – Runs on-premises or on a VM for hybrid/cloud connectivity.
  - `SSIS IR` – Executes SSIS packages in ADF.


### 3. Pipelines and Activities in ADF
**Pipeline:**
A data factory might have one or more pipelines. A pipeline is a logical grouping of activities that performs a unit of work.
For example, a pipeline can contain a group of activities that ingests data from an Azure blob, and then runs a Hive query on an HDInsight cluster to partition the data.

**Activity:**
Activities represent a processing step in a pipeline. For example, you might use a copy activity to copy data from one data store to another data store.

Data Factory supports three types of activities: `data movement activities`, `data transformation activities`, and `control activities`.

#### 1. Data Movement Activities:
- `Copy Data Activity` - Moves data from source to destination, supporting over 90+ data stores, including SQL, Blob, ADLS, and external sources like Snowflake and AWS S3. Use Case: Loading data from an on-prem SQL Server to Azure Data Lake.

#### 2. Data Transformation Activities
- `Mapping Data Flow` - Provides a no-code, GUI-based transformation similar to SSIS, with options like joins, aggregations, and derived columns.
- `Stored Procedure Activity` -  Calls SQL stored procedures for data processing.
- `Databricks Activities`:
  - Notebook Activity – Executes Databricks notebooks for transformation.
  - Jar Activity – Runs Scala/Java JAR files.
  - Python Activity – Executes Python scripts in Databricks.
- `HDInsight Activities:`
  - Hive, Pig, MapReduce, Spark – Runs big data processing jobs.
- `Azure Functions:` Runs on Azure Functions compute environment.
- `U-SQL:` Runs on Azure Data Lake Analytics compute environment.

#### 3. Control Flow Activities (Orchestration)
Control Flow Activities in ADF help in managing the execution logic of pipelines by controlling the flow between different activities. These activities enable conditional execution, looping, error handling, and external interaction.

- `ForEach Activity` – This activity is used to iterate over a collection and executes specified activities in a loop.
- `If Condition Activity` – Executes based on a boolean condition.
- `Filter	Activity` - Apply a filter expression to an input array
- `Switch Activity` – Routes execution based on an input value.
- `Wait Activity` – Introduces a delay (useful for dependency management).
- `Execute Pipeline Activity` – Triggers another ADF pipeline.
- `Until Activity` – Loops until a condition is met.
- `Set Variable & Append Variable` – Dynamically sets and appends values.
- `Get Metadata` - GetMetadata activity can be used to retrieve metadata of any data in a Data Factory or Synapse pipeline.
- `Append Variable` - Add a value to an existing array variable. 

### 3. What do you mean by data source in ADF?
It is the source or destination system which contains data to be used or operate upon.

ADF supports data of any type like text, binary, json, csv types files or may be audio, video, image files.

Data Soruc examples are: Azure blob storage, azure data lake storage,  any database like azure sql database, mysqldb, postgres and etc.

### 4. What are linked services in ADF, and why are they used?
Linked services in ADF represent connections to external data sources, such as Azure Blob Storage, Azure SQL Database, or onpremises SQL Server. Integration runtime: Provides access to internal compute resource inside Azure Data
Factory. ADF has no internal storage resources.

They are used to define the connection strings and credentials required to access these data stores.

### 5. What is the Datasets in Azure Data Factory?
A dataset in Azure Data Factory (ADF) is a named view of data that simply points or  references the data you want to use in your activities as inputs and outputs. You need a linked service to create dataset.

Contains metadata describing a specific set of data held in an external storage system.
Pipeline activities use datasets to interact with external data

### 6. What is an Integration Runtime (IR) in ADF?
Integration Runtime (IR) is the compute infrastructure used by ADF to perform data Integration activities such as data movement, data transformation, and data flow execution. It acts as the bridge between ADF and the data sources or destinations, enabling connectivity and operational execution.

IR is the heart of Azure data factory.

### 7. What are mappig data flows?
Mapping Data Flows in ADF are visually designed data transformation tools without writing any code. You can develop data transformations logic without wrting any code.

They allow users to build data transformation logic graphically and execute the workflows in a scalable and optimized manner using ADF's Azure Integration Runtime. It is executed over Apache Spark clusters under the hood.

### 8. What are the triggers in ADF?
In ADF, triggers are scheduling mechanisms that initiate the execution of pipelines. Triggers represent a unit of processing that determines when a pipeline execution needs to be kicked off.

They allow you to define when and how pipelines should run based on any date time, frequency or based on some event like file creation/deletion providing flexibility in automating data workflows.

### 9. What is a copy activity in ADF?
The Copy Activity is a core data movement activity used to copy data from a source data store to a destination data store.
It is a fundamental part of building data pipelines in ADF and is often used for Extract, Load, and Transform (ELT) processes.

### 10. what is a debug in ADF?
In Azure Data Factory (ADF), "debug" refers to a feature that allows you to test and troubleshoot individual activities or entire pipelines within your data flow by running them in a controlled environment, enabling you to inspect data at each step and identify any errors or issues before fully deploying your pipeline to production

You can run a pipeline interactively from the ADF UX using “Debug” mode.

# Level 2 Interview Questions

### 11. What is the difference between trigger and debug?
Triggers are way to schedule automated pipeline execution. While debug is used to test the pipeline by manually executing.

In debug we can add the debug point to ensure, it will execute the pipeline up to debug point only. Logs also got separately for trigger and debug executions.

### 12. what is the variable in the ADF Pipeline?
Variables are used to store values that can be used within a pipeline during execution. Variables are used to hold the temporary values within the pipeline scope. Variables are defined at the pipeline level.

Variables value can be set at runtime using the set variable activity.

### 13. What are the pipelne parameters in ADF?
Pipeline parameters are used to provide the the value at execution time. It is like a runtime parameter.

Pipeline Parameters in Azure Data Factory (ADF) are user-defined values that allow pipelines to be dynamic and reusable. They act as placeholders for values that are passed into a pipeline during execution, enabling customization of pipeline behavior at runtime.

### 14. what is the difference variable and parameter in ADF?
In ADF, Variables store temporary values within a pipeline and can be changed/updated during execution while Parameters are placeholders for values passed into a pipeline at runtime.

Variables used to store intermediate values or manage state during pipeline execution and parameters used to pass input values to a pipeline for dynamic behavior or configuration.

### 15. what are the global parameters in ADF?
Global Parameters are user-defined parameters that are available across all pipelines within a Data Factory. 

Unlike pipeline parameters, which are scoped to individual pipelines, global parameters are defined at the Data Factory level and can be reused in multiple pipelines, making them useful for common configurations and settings.

### 16. At how many level parameterization can be done in ADF?
In Azure Data Factory (ADF), parameterization can be done at five levels:

1. **Global Parameters:** Defined at the account level, these parameters can be reused across multiple pipelines, datasets, and linked services for consistent values.
2. **Pipeline Level:** Parameters defined within a specific pipeline to pass values to activities within that pipeline.
3. **Activity Level:** Each activity can have its own parameters that can be parameterized based on pipeline parameters or other inputs.
4. **Dataset Level:** Datasets can be parameterized to allow dynamic configuration of properties like file paths or connection strings.
5. **Linked Service Level:** Linked services can also have parameters for dynamic connection information.

### 17. what are the Azure Data Factory user properties?
User properties are metadata attributes that you can define for various ADF entities such as pipelines, datasets, and linked services. These properties allow you to add custom information to your ADF objects, which can be useful for tracking, documentation, or management purposes.

By adding user properties, you can view additional information about activities under activity runs. You can have upto 5 user properties per activity.

### 18. what are Annotations in ADF?
Annotations are addtional, informative tags that you can add to specific factory resources like pipelines, datasets, linked services and triggers.

By adding annotations, you can easily filter and search for specific factory resources.

### 19. what is the difference between ADF user properties and annnotations?
In Azure Data Factory, `annotations` are static values and tags that help you group and organize objects (`pipelines`, `datasets`, etc.) while `user properties` are defined within the Azure Data Factory activities and the values can change during execution.They help you measure performance for pipeline activities

User properties defined at activity level, while annotation can be at linked service, dataset, trigger level.

### 20. what are the different types of Integration Runtime in ADF?
There are three main types of Integration Runtime in ADF, each serving different purposes:

#### 1. Azure Integration Runtime:
- Fully Managed by Azure
- Suitable for cloud-to-cloud data movement and cloud-based activities
- Can be used with public or private endpoints
- Offers features like auto-scaling and high availability

#### 2. Self-hosted Integration Runtime:
- Deployed and managed on your own infrastructure (on-premises or in a virtual network)
- Provides connectivity to on-premises data sources and resources
- Offers more control and customization compared to Azure IR

#### 3. Azure-SSIS Integration Runtime:
- A specialized version of the Azure IR designed to host and execute SQL Server Integration Services (SSIS) packages in the cloud
- Enables you to lift and shift existing SSIS workloads to the cloud

# Level 3 Interview Questions

### 21. Is it mandatory to create IR in ADF? Explain why?
No it is not mandatory. Because you will get one IR i.e. `autoresolveintegrationruntime` by default once you create azure data factory.

Subsequently you can use this IR in variety of the linked service.

### 22. Assume that you want to call one pipeline from another pipeline. Is it possible. If yes how?
Yes it is possible.

There is activity called as `execute pipeline` activity. We can add this activity within the parent pipeline and call the child pipeline through it.

### 23. Assume that you are pulling data from on-premise DB server for multiple tables using copy activity inside the foreach. How you can ensure that on-prem server you will send only one DB request at a time?

Ans: In the `foreach` activity we have option to run it in sequential manner. Once we set it as true, then every iteration will go in sequential manner. It will avoid the load on the DB server.

### 24. Assume that you are working as data engineer for xyz company. Company wanted to do cloud migration from their on-premises to Microsoft Azure cloud. You probably will use the Azure data factory for this purpose. You have created a pipeline that copies data of one table from on-premises to Azure cloud. What are the necessary steps you need to take to ensure this pipeline will get executed successfully?

- First and foremost requirement is to have `self-hosted integration runtime` as data has to move between the on-prem to cloud.
- Once selfhosted IR get created and up running, create the linked service which will use this self-hosted IR to make connection to on-prem server.
- Then create pipeline, add copy activity and create respective dataset to move the data between source and destination.

### 25. Assume that you have Azure SQL db defined in US-East region and you have to move the data to ADLS in the same region. But you have a compliance issue that data shouldn't move outside the region. How would you ensure while using the ADF copy?

Create an Azure Integration Runtime with region as US-East and use it to create both the linked services (one for DB and other for ADLS).

If you don't do this, then by default `autoresolveIR` will be used. Although Azure will try to assign it within the same region, there is no guarantee. Hence create your own IR and use it.

### 26. Assume that you are working as data engineer at xyz company. There you got business requirement in such a way that, it needed for loop inside for each. However ADF doesn't support nested foreach (at the moment). How you can tackle this situation?

We will create two separate pipeline where each has one `foreach` activity. Then we will add the execute pipeline activity to call the second pipeline from inside the first pipeline's foreach activity.

### 27. Assume that you are working as data engineer at Azurelib.com. You have tested your pipeline and all working well in dev env. How would you move it next env like UAT/prod? What is the best practice you follow in your project?

We integrate ADF with azure devops git. We create separate branch for every env in the Git repo. Once development is done we raise the pull request to merge the code in next branch (UAT/Prod).

In the devops we will create the release pipeline which will pull the code from the UAT/prod branch and deploy automatically to respective env.

### 28. Assume that your pipelines are deployed on prod. Suddenly one day you have been informed that it stopped working. What will you do in this situation?

I will go to monitor tab. There I can filter out and see the execution history for the given pipeline. I will check the specific failure execution go inside and see the error. I will try to check at which activity it got failed. I will check input to this activity and see is it getting expected input and what is the error look like.

### 29. Assume that you have to pull the data from on-prem db to the Azure SQL db on the daily basis in the incremental manner. How would you create incremental pipeline?

We will create a incremental pipeline using the `highwatermark concept.`

**Steps:**
Create file or a table as highwatermark file/table to keep last execution date.

Put very old date in file/table.

Now create a pipeline with having following activity:
- Lookup activity to get last execution date from table/file.
- Lookup activity to get last update record from source table.
- Pull the data between these two dates and copy using copy activity.
- Update the highwatermark table/file with date from step 2.

### 30. Assume that there is a business requirement. An external application drops the file in the blob storage account. Your pipeline has to pick this file and push the data into the Azure SQL database. How would you design the solution?

Create a pipeline with a copy activity to move the data from blob to Azure SQL DB. However, the key here is the triggering of the pipeline. We need to use the storage event-based trigger to execute the pipeline as soon as the file arrives.

### 31. Assume that there is a business requirement. Your pipeline is copying the data from source to destination. However, you want to receive an email notification whenever this copy activity fails. How would you design this solution?

- Create a pipeline with a copy activity.
- Create a logic app which will have trigger as REST API.
- Logic app will have email as action. It will send an email to defined name, subject, and message.
- Now in the pipeline, add one web activity which will call the logic app as REST API.
- Connect this web activity to copy activity for failure scenario.

### 33. Assume that you are developing a pipeline. Your pipeline is copying the data from source to destination (ADLS). This pipeline runs on a daily basis. You have to create a folder hierarchy (year/month/day) and store files inside it. How would you design this solution?

We will use the dynamic content for folder path. Using the function like **formatDateTime(utcnow(), 'yyyy')** gives you year then concatenate it with month and day.
  ```sql
  @concat(formatDateTime(utcnow(), 'yyyy'), '/', formatDateTime(utcnow(), 'MM'), '/',   formatDateTime(utcnow(), 'dd'))
  ```

### 34. Assume that you are developing a pipeline. Your pipeline is copying the data from REST api source to destination (ADLS). This pipeline runs on a daily basis. Your rest endpoints are dynamic as: https://www.rohishzade.com/dd-mm-yy. How would you design this solution?
- Create a pipeline.
- Add copy activity
- Add a linked service as REST type by giving the base URL:
  - https://www.rohishzade.com/
- Add a REST type of dataset. There under relative URL column put the dynamic content like:
  - ```sql 
    @concat(formatDateTime(utcnow(), 'dd'), '-', formatDateTime(utcnow(), 'MM'), '-', formatDateTime(utcnow(), 'yyyy'))
    ```
### 35. Assume that there multiple files in ADLS folder. All of these files have file name corresponding to a table in DB? Example customer.txt, product.txt You have to copy the data from these files to respective tables automatically. How would you design the solution?
- Create a pipeline.
- Put `GetMetaData` activity to get list of all files within the folder.
- Use forEach loop to iterate upon it.
- Inside foreach add the copy activity to copy the data from ADLS to DB.
- Here keep the DB dataset parameterized to pass the table name as the filename.
- This will make the entire process dynamic. 

### 36. In which scenario you will going to use the linked self hosted IR?
Linked Self-hosted IR are the integration runtime linked from external or different data factory account to current ADF account.

Assume, there is one separate team who is pulling the data from some on-prem db and for that they have already created self-hosted IR by setting up infra.

Now rather setting new infra, you can refer the same.

### 37. Assume that you copying the data from file to table using ADF? Now there are few rows not matched with table schema. Hence due to that copy activity is failing. How you deal with such scenarios?

In the copy activity we can enable `logging`. There we can set `skipping unmatched rows` and continue. We can log all those skipped rows to a file in adls as well.

### 38. Assume that you copying the data from file to table using ADF? It is working very slow. What you can do improve the performance?

In the copy activity setting tab we have DIU (`data integration unit`). By default it is auto. That means it will auto scale starting from 4. To improve the performance we can assign some high value since the start. This could speed up the work.

We can also use the staging concept in case of certain data sources as well.

### 39.  What are the scenarios where copy activity's mapping configuration would be useful?

In the copy activity mapping tab we can set mapping between the source to destination. Now assume that in source column name is 'Cost' and in destination column name is 'Price'.

Then you can exclusively define which source column mapped to destination column.

### 40. Assume that your pipeline got failed at second activity. To avoid data inconsistency you have wanted to rerun the pipeline from failed activity. Can we do this? Give reason.

Yes we can do it. Go to Monitor -> search pipeline -> open -> run from failed activity.
