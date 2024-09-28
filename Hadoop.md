# What is Apache Hadoop?
- Hadoop is an open-source framework for distributed storage and distributed
processing of large data sets.
- It's designed to scale up from single servers to thousands of machines, offering local storage and computation.
- It is designed to run on clusters of commodity hardware, allowing it to handle big data workloads with high fault tolerance and scalability.
- It also allows the system to continue operating in case of node failure.


### Main Components of Hadoop?
- Storage layer – **HDFS**
- Batch processing engine – **MapReduce**
- Resource Management Layer – **YARN**

**HDFS:** 
- HDFS (Hadoop Distributed File System) is the storage unit of Hadoop. 
- It is responsible for storing different kinds of data as blocks in a distributed environment.- It follows master and slave topology.
- Components of HDFS are `NameNode` and `DataNode`.

**MapReduce:**
- For processing large data sets in parallel across a hadoop cluster, Hadoop MapReduce framework is used.
- Data analysis uses a two‐step `map` and `reduce` process.

**YARN:**
- YARN (Yet Another Resource Negotiator) is the processing framework in Hadoop, which manages resources and provides an execution environment to the processes.
- Main Components of YARN are `Node Manager` and `Resource Manager`.


### Why do we need Hadoop?
- **Cost-Effective Storage:** It offers affordable storage and processing using commodity hardware.
- **Scalability:** Hadoop scales horizontally by adding more nodes as data grows.
- **Fault Tolerance:** Data is replicated across nodes, ensuring availability even during hardware failures.
- **Parallel Processing:** It processes large datasets in parallel, reducing computation time.
- **Data Flexibility:** Hadoop supports structured, semi-structured, and unstructured data.
Open-Source Ecosystem: A free and evolving ecosystem with a wide range of tools for big data processing.
- **Data Locality:** It processes data locally on the nodes where it's stored, enhancing efficiency.


### What are the four characteristics of Big Data?

- **Volume:** The volume represents the amount of data which is growing at an exponential
rate i.e. in Petabytes and Exabytes
- **Velocity:** Velocity refers to the rate at which data is growing, which is very fast. Today, yesterday’s data are considered as old data. Nowadays, social media is a major contributor in the velocity of growing data.
- **Variety:** Variety refers to the heterogeneity of data types. In another word, the data which are gathered has a variety of formats like videos, audios, csv, etc. So, these various formats represent the variety of data.
- **Veracity:** The accuracy, quality, and trustworthiness of the data.
- **Value:** It is all well and good to have access to big data but unless we can turn it into a value it is useless.


### What are the modes in which Hadoop run?
Hadoop can run in three different modes:

1. **Standalone Mode (Local Mode):** Default mode, where Hadoop runs on a single machine without using HDFS or MapReduce.

2. **Pseudo-Distributed Mode:** Simulates a distributed environment on a single machine, where each Hadoop daemon runs as a separate process.

3. **Fully Distributed Mode:** Hadoop runs on a cluster of machines with full HDFS and MapReduce functionality, distributing data and tasks across multiple nodes.



## Architecture of Hadoop

Hadoop follows a `master-slave` architecture and consists of four primary components:

![](https://github.com/rohish-zade/Big-Data-Interview-Preparation/blob/main/images/hadoop-architecture.png)


### HDFS (Hadoop Distributed File System):
- HDFS is the `storage layer` of Hadoop. 
- It splits large files into smaller chunks (blocks) and distributes them across a cluster of machines (nodes). 
- Each block is replicated multiple times (default is 3) for fault tolerance. 
- If a node fails, the data can still be accessed from other nodes that hold its replicas.

#### Components:
- **NameNode:** Acts as the master node that manages the metadata of the file system (e.g., file names, block locations). It does not store actual data but keeps track of where data blocks are located on the cluster.

- **DataNodes:** The slave nodes that store the actual data. DataNodes periodically send heartbeats to the NameNode to signal that they are functioning properly.

- **Secondary NameNode:** Not a backup of the NameNode, but it helps in managing NameNode metadata by taking snapshots of file system metadata and merging edit logs to prevent NameNode failures.

### MapReduce:
- MapReduce is the `data processing layer` of Hadoop, responsible for running computation on large datasets in parallel. 
- It follows a `divide-and-conquer` approach where data is split into smaller subsets, processed on different nodes, and results are aggregated.
- MapReduce helps Hadoop process large datasets efficiently by utilizing the distributed nature of the cluster.

#### How it Works:
- **Map Phase:** Breaks the input data into smaller key-value pairs and processes them in parallel across the nodes.

- **Reduce Phase:** Aggregates the results of the map tasks by combining intermediate outputs into final results.


### YARN (Yet Another Resource Negotiator):
- YARN is the resource management layer of Hadoop, introduced in Hadoop 2.x. 
- It decouples the task of resource management and job scheduling from MapReduce.

#### Components:
- **ResourceManager:** Allocates system resources (CPU, memory) to various applications running in the cluster.
- **NodeManager:** Manages resources on individual nodes and reports resource usage to the ResourceManager.
- **ApplicationMaster:** Each application has its own ApplicationMaster that negotiates resources from the ResourceManager and works with NodeManagers to execute tasks.


### Hadoop Common:
- This includes the common utilities and libraries that support the other Hadoop modules.
- These utilities ensure that the different components of Hadoop can work together seamlessly.


## What is Rack Awareness in Hadoop?
- Rack Awareness in Hadoop is a method used to decide where to store data and its copies based on the physical locations of the servers in a data center. 
- It organizes servers into groups called racks.
- Hadoop uses this concept to optimize network bandwidth usage and enhance fault tolerance.

**Physical Location:**
- Nodes in a Hadoop cluster are organized into racks.
- A rack is a physical unit containing multiple servers (nodes), typically within the same data center.

**Network Optimization:**
- Communication between nodes within the same rack is faster than between nodes in different racks.
- By considering the rack location of nodes, Hadoop minimizes network traffic.

**Fault Tolerance:**
- Hadoop places copies (replicas) of data blocks on different racks.
- This ensures that, in case of a rack failure (power or network issues affecting the entire rack), data is still accessible from replicas stored on other racks.

**Example of Rack Awareness in Action:**

If a file is stored with a replication factor of 3, Hadoop will place:
- One replica on the same rack as the original data.
- The second replica on a different rack (to ensure redundancy).
- The third replica on another node in the same or a different rack to balance performance and fault tolerance.



## Interview Questions and answers on HDFS:
What is HDFS?
- Answer: HDFS (Hadoop Distributed File System) is the storage component of Hadoop designed to store large datasets across multiple nodes with fault tolerance, high throughput, and scalability.

How does HDFS ensure fault tolerance?
- Answer: HDFS ensures fault tolerance by replicating data blocks across multiple nodes. By default, each block is replicated three times, so if one node fails, the data is still accessible from the other nodes.

What is the role of NameNode in HDFS?
- Answer: The NameNode is the master node in HDFS that manages metadata like file locations, block mapping, and directory structure. It does not store the actual data but keeps track of where data is stored on the cluster.

What is a DataNode in HDFS?
- Answer: DataNodes are slave nodes that store the actual data in HDFS. They periodically send heartbeats and block reports to the NameNode to ensure they are functioning correctly and the data is available.

What is block in HDFS, and why is it large (default 128MB)?
- Answer: A block in HDFS is the minimum unit of data storage. Large block sizes (128MB or 256MB) minimize the overhead of block management and reduce the number of seeks, making it efficient for storing and processing large files.

What is the Secondary NameNode?
- Answer: The Secondary NameNode helps by taking periodic snapshots of the NameNode’s metadata and merging the edit logs with the file system image to prevent the NameNode from overloading. It is not a backup NameNode.

What happens if the NameNode fails in HDFS?
- Answer: If the NameNode fails, the HDFS cluster becomes unavailable because it manages the file system metadata. Starting with Hadoop 2.x, NameNode High Availability (HA) can be configured with a standby NameNode to prevent downtime.

What is fsck in HDFS?
- Answer: fsck (File System Check) is a command used to check the health of the HDFS file system, detect corrupt files or blocks, and verify if files are correctly replicated.

What is data locality in HDFS?
- Answer: Data locality refers to the concept where Hadoop moves computation to the node where the data resides, reducing network overhead and improving performance by processing data locally.

How can you access HDFS files in Hadoop?
- Answer: HDFS files can be accessed using the Hadoop command-line interface (CLI), the Hadoop web UI, or programmatically using APIs such as the Hadoop FileSystem API.

What is the difference between HDFS and traditional file systems?
- Answer: HDFS is designed to handle large files across multiple nodes in a distributed manner with high fault tolerance, while traditional file systems are designed for smaller data sets and typically reside on a single machine.

What is the default replication factor in HDFS, and how can you change it?
- Answer: The default replication factor is 3. It can be changed at the file level using the hdfs dfs -setrep command or globally in the hdfs-site.xml configuration file.

What happens when a DataNode fails in HDFS?
- Answer: When a DataNode fails, the NameNode re-replicates the lost data blocks to other DataNodes to maintain the specified replication factor, ensuring data availability and fault tolerance.

Can you write directly to HDFS?
- Answer: Yes, you can write directly to HDFS using the command-line interface (hdfs dfs -put or hdfs dfs -copyFromLocal) or programmatically using the Hadoop API.

What are the key differences between HDFS and NFS (Network File System)?
- Answer: HDFS is designed for high throughput and fault tolerance with large files distributed across multiple machines, while NFS is designed for low-latency access to smaller files stored on a single or few machines.

How does HDFS handle small files?
- Answer: Small files are inefficient in HDFS since each file is treated as a block and requires metadata management. Tools like Hadoop Archive (HAR) or HBase can be used to group small files together and reduce the overhead.

What are the steps to perform a safe shutdown of NameNode and DataNode?
- Answer: First, run stop-dfs.sh to stop the HDFS services. Then, to safely shut down the NameNode and DataNode, ensure all pending jobs are complete and gracefully stop services using Hadoop commands or the web interface.


## Interview Questions and answers on Hadoop MapReduce:

What is MapReduce?
- Answer: MapReduce is a programming model and processing engine in Hadoop that allows for the distributed processing of large datasets across a cluster by dividing the workload into smaller tasks, specifically the "Map" and "Reduce" tasks.

Explain the MapReduce process.
- Answer: The MapReduce process consists of two main phases:
  - `Map Phase:` Input data is processed by the Mapper function to produce key-value pairs.
  - `Reduce Phase:` The output from the Mappers is aggregated by the Reducer function to produce the final result.

What are the main components of MapReduce?
- Answer: The main components of MapReduce are:
  - `Mapper`: Processes input data and produces intermediate key-value pairs.
  - `Reducer`: Aggregates intermediate key-value pairs produced by Mappers.
  - `JobTracker`: Manages the execution of the MapReduce jobs.
  - `TaskTracker`: Executes the tasks assigned by the JobTracker.

What is the difference between a Mapper and a Reducer?
- Answer: A `Mapper` processes input data to generate intermediate key-value pairs, while a `Reducer` takes those pairs, groups them by key, and performs aggregation or computations to produce the final result.

What is a combiner in MapReduce?
- Answer: A `combiner` is an optional mini-reducer that processes the output of the Mapper before it is sent to the Reducer. It helps to reduce the amount of data transferred over the network, improving performance.

What are the types of input formats in MapReduce?
- Answer: Common input formats in MapReduce include:
  - `TextInputFormat`: Reads lines of text files.
  - `KeyValueTextInputFormat`: Reads key-value pairs from text files.
  - `SequenceFileInputFormat`: Reads binary key-value pairs from sequence files.
  - `NLineInputFormat`: Reads a specific number of lines from input files.

What is the output format in MapReduce?
- Answer: The output format defines how the output of the MapReduce job will be written. - - - - Common output formats include:
  - `TextOutputFormat`: Writes output as plain text.
  - `SequenceFileOutputFormat`: Writes output as a sequence of binary key-value pairs.
  - `JSONOutputFormat`: Writes output in JSON format.


How does MapReduce handle failures?
- Answer: MapReduce automatically retries failed tasks, reassigning them to other nodes. If a task fails multiple times, the JobTracker marks it as failed and may notify the user.


What is the shuffle and sort phase in MapReduce?
- Answer: The `shuffle` and `sort` phase occurs between the Map and Reduce phases. It involves transferring the output of the Mappers to the Reducers, sorting the data by key, and grouping all values associated with the same key for processing by the Reducer.

Can you explain the input and output of a MapReduce job?
- Answer: The input of a MapReduce job consists of raw data files (e.g., text files in HDFS), while the output is typically a set of key-value pairs written to a specified output location in HDFS, generated by the Reducer.

What are the advantages of using MapReduce?
- Answer: Advantages of MapReduce include:
  - `Scalability` to process large datasets across clusters.
  - `Fault tolerance` through automatic task retries.
  - `Efficient` use of resources by distributing processing.
  - `Flexibility` to work with various data formats.


What programming languages can be used to write MapReduce jobs?
- Answer: MapReduce jobs are typically written in `Java`, but other languages like `Python` (using Hadoop Streaming), `R`, and `Ruby` can also be used through specific APIs or libraries.


## Interview Questions and answers on YARN:

What is YARN?
- Answer: YARN (Yet Another Resource Negotiator) is a resource management layer in Hadoop that manages and schedules resources for various applications running on a Hadoop cluster, allowing for multi-tenancy and improved cluster utilization.

What are the main components of YARN?
- Answer: The main components of YARN are:
  - `ResourceManager`: The master daemon responsible for managing resources across the cluster and scheduling applications.
  - `NodeManager`: The worker daemon that runs on each node, managing resources and monitoring resource usage for containers.
  - `ApplicationMaster`: A per-application instance that negotiates resources from the ResourceManager and coordinates the execution of tasks.

What is the role of the ResourceManager in YARN?
- Answer: The `ResourceManager` is responsible for allocating cluster resources to various applications, maintaining the resource availability information, and scheduling the applications based on defined policies.


what is the role of the NodeManager in YARN?
- Answer: The `NodeManager` is responsible for managing resources on individual nodes, monitoring resource usage, and launching and managing containers (processes) as instructed by the ResourceManager.


What is the ApplicationMaster in YARN?
- Answer: The `ApplicationMaster` is a framework-specific component that manages the lifecycle of an application, negotiating resources from the ResourceManager and coordinating the execution of tasks within the allocated containers.


What are the advantages of YARN?
- Answer: Advantages of YARN include:
  - Improved resource management and utilization.
  - Support for multiple processing frameworks (e.g., Spark, Tez).
  - Enhanced scalability and flexibility for running different applications.
  - Better fault tolerance and job recovery mechanisms.


How does YARN improve Hadoop's scalability?
- Answer: YARN separates resource management from job scheduling, allowing multiple applications to run concurrently on a Hadoop cluster, improving resource utilization and enabling better scalability for diverse workloads.


What are containers in YARN?
- Answer: Containers are the basic unit of resource allocation in YARN, encapsulating the resources (CPU, memory, disk) needed to run a task or an application. Each container runs a single task and is isolated from other containers.


What is the difference between YARN and traditional MapReduce?
- Answer: Traditional MapReduce has a fixed resource management model tightly integrated with job execution, while YARN decouples resource management and job scheduling, allowing for more flexible resource allocation and support for various processing frameworks beyond MapReduce.


What is the Scheduler in YARN?
- Answer: The Scheduler is a component of the ResourceManager that allocates resources to different applications based on scheduling policies (e.g., CapacityScheduler, FairScheduler) without taking application-specific logic into account.


What is the Capacity Scheduler in YARN?
- Answer: The `Capacity Scheduler` is a resource allocation policy in YARN that allows multiple organizations to share a Hadoop cluster. It ensures that each organization can use a defined percentage of the cluster’s capacity.

What is the Fair Scheduler in YARN?
- Answer: The `Fair Scheduler` is a resource allocation policy in YARN that allocates resources to applications in a way that aims to ensure that all applications receive a fair share of resources over time.


How does YARN handle failures?
- Answer: YARN handles failures by monitoring the health of NodeManagers and ApplicationMasters. If a NodeManager fails, the ResourceManager can reassign the containers to other healthy nodes. If an ApplicationMaster fails, it can be restarted.


What is a YARN Resource Pool?
- Answer: A YARN Resource Pool is a defined set of resources that can be allocated to different applications. Pools can be configured to limit the maximum resources used by applications, allowing for fair resource sharing among users.


What is Node Labeling in YARN?
- Answer: Node labeling allows administrators to categorize nodes in a YARN cluster based on specific attributes (e.g., hardware capabilities). Applications can then request resources from specific labeled nodes, improving resource utilization


What is the difference between the ResourceManager and NodeManager?
- Answer: The `ResourceManager` is the master daemon responsible for managing resources across the cluster and scheduling applications, while the `NodeManager` is a worker daemon running on each node that manages the execution of containers and resource usage on that node.


How can you monitor YARN applications?
- Answer: YARN applications can be monitored using the YARN ResourceManager `web UI`, `command-line tools` (like yarn application -list), and `logs` provided by NodeManagers for task execution status and resource usage.