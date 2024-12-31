# Level 1 Interview Questions

### 1. What is Azure Data Factory (ADF)?
Azure Data Factory is a cloud-based ETL service that allows you to create data-driven workflows for orchestrating and automating data movement and data transformation.

#### Common Use Cases for ADF:
- **ETL and ELT Pipelines:** Extracting data from various sources, transforming it, and loading it into data lakes or warehouses.
- **Data Migration:** Moving data between on-premises systems and cloud environments.
- **Orchestration and Automation:** Allows the scheduling and monitoring of pipelines for automated data processing.
- **Data Lake Integration:** Populating and processing data within Azure Data Lake.
- **Analytics Preparation:** Preparing and aggregating data for use in business intelligence and machine learning workflows.

#### Why Use Azure Data Factory?
Azure Data Factory simplifies the process of managing complex data workflows and eliminates the need for infrastructure management. Its flexibility, rich integrations, and scalability make it an essential tool for modern data-driven organizations.

### 2. What is the Pipeline in ADF?
In ADF, a pipeline is a logical grouping of activities that work together to perform a specific task.

#### Key Components of an ADF Pipeline:
- `Activities:` Activities represent the tasks or operations performed in the pipeline, such as copying data, running a transformation, or executing a script.
- `Linked Services:` Connections to data sources and compute resources.
- `Datasets:` Represent data structures used as inputs or outputs for activities.
- `Triggers:` Schedule or invoke pipelines based on time or events.
- `Parameters:` Enable dynamic and reusable pipeline configurations.
- `Control Flow:` Orchestrates execution logic like sequencing, conditions, and loops.

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

### 30.

### 31.

