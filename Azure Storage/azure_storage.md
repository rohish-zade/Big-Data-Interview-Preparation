### 1. What is Azure Storage?
- It is Cloud storage solution for modern data storage scenarios.
- It works whether you want to store the data of any format like images, csv, text, audio, video, binary files.
- You can access data stored in storage account in multiple ways like through https, in programmtic manner through rest APIs or through powershell commands.

### 2. what are the benefits of Azure Storage?
Azure Storage offers several benefits that align well with the needs of data engineering projects:
- **Durable and highly available:** Azure Storage ensures data durability with redundancy options like LRS, ZRS, and GRS, offering high availability even during failures.
- **Secure:** It provides encryption at rest and in transit, role-based access control (RBAC), and integration with Azure Active Directory for enhanced security.
- **Scalable:** Azure Storage can seamlessly scale to handle massive data volumes, making it suitable for high-demand workloads.
- **Managed:** Fully managed service that eliminates the overhead of hardware maintenance and supports automated backups and updates.
- **Accessible:** Supports various protocols and APIs, making it easy to access data from applications, devices, and Azure services.


### 3. what are the different Azure Storage data services
Microsoft Azure Storage offers various data services for storing and accessing data in the cloud:

#### 1. Azure Blob Storage:
- Object store for text and binary data
- Designed for storing unstructured data like images, documents, audio, and video files. It's highly scalable, allowing you to store petabytes of data.
- Includes support for big data analytics through Data Lake Storage Gen2 (ADLS).

#### 2. Azure Files: 
- Managed file shares for cloud or on-premises deployments.

#### 3. Azure Queues:
- A messaging store for reliable messaging between application components.
- It is a service for stroing large number of messages.

#### 4. Azure Tables:
- A NoSQL store for schemaless storage of structured data.
- Serive that stores non-relational structured data(No-SQL data)
- It is schemaless, fast and cost effective

#### 5. Azure Disks:
- Block-level storage volumes for Azure VMs.
- Persistent block-level storage that attaches virtual disks to Azure virtual machines.
- It offers two options: **premium** and **standard** storage, with both offering Azure managed and unmanaged disks

#### 6. Azure Data Lake Storage Gen2 (ADLS Gen2)
- Combines the best features of Azure Blob Storage and ADLS Gen1.
- Built on top of Azure Blob Storage to unify object storage and data lake capabilities.
- Hierarchical Namespace: Supports directory structures, enabling efficient management of data similar to file systems.


### 4. what is Azure Blob Storage
- Azure Blob Storage is a cloud-based storage service that allows users to store and manage large amounts of unstructured data in the cloud. 
- It is designed to store large amounts of unstructured data, such as text or binary data.

#### Key Features:
- **Massive Scalability:** Stores petabytes of data.
- **Redundancy Options:** Offers LRS, ZRS, GRS, and RA-GRS for durability and availability.
- **Access Tiers:** Hot (frequent access), Cool (infrequent access), Archive (rare access).
- **Security:** Data encryption, RBAC, and SAS for controlled access.
- **Integration:** Works with Azure services like Synapse Analytics and Data Lake Storage Gen2.

#### Types of Blobs:
- **Block Blobs:** Store large files like media or documents.
- **Append Blobs:** Optimized for logging and incremental data addition.
- **Page Blobs:** Used for random access, such as Azure VM disks.

#### Use Cases:
- **Big data analytics:** Blob Storage can be used to store and process data for big data analytics and machine learning
- **Storing large amounts of unstructured data:**  Blob Storage is a cost-effective option for storing data that doesn't need to be accessed frequently. This includes photos, videos, audio files, and papers.
- **Backup and disaster recovery:** Blob Storage is well-suited for backing up large data sets, especially for recovering from ransomware attacks.
- **Hosting and streaming:** Blob Storage can be used to host and stream images, audio files, and videos.
- **Logging:** Blob Storage can be used to store log file objects and telemetry data for monitoring, debugging, or analytic purposes. 
- **Long-term data archiving:** It offers different access tiers whhich makes suitable for long term data archiving.

