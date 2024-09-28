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