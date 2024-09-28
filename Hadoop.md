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



