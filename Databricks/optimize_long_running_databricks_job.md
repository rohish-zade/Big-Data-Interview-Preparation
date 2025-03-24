# How do you optimize Spark jobs in Azure Databricks?

Optimizing a long-running **Databricks job** requires improvements in Spark performance, cluster tuning, and job orchestration. Here are key strategies:



## **1. Optimize Data Processing**
### **a) Use DataFrame API Instead of RDDs**
- PySpark **DataFrames** are optimized with **Catalyst Optimizer** and **Tungsten Engine**.
- Avoid using RDDs unless necessary.

### **b) Use `.select()` Instead of `*`**
- Always select only the required columns.
- Example:
  ```python
  df = df.select("col1", "col2")
  ```

### **c) Optimize Joins**
- Use **broadcast joins** for small tables:
  ```python
  from pyspark.sql.functions import broadcast
  df = df1.join(broadcast(df2), "id")
  ```
- Use **bucketing** for large joins:
  ```python
  df.write.bucketBy(10, "id").saveAsTable("bucketed_table")
  ```

### **d) Optimize File Format**
- Prefer **Parquet** or **Delta** instead of CSV/JSON.
- Delta format allows **Z-Ordering** and **data skipping**.



## **2. Optimize Cluster Configuration**
### **a) Autoscaling**
- Enable autoscaling to dynamically allocate resources based on load.
- Set worker node limits appropriately.

### **b) Use the Right Cluster Mode**
- **Standard Mode**: Best for general workloads.
- **High Concurrency Mode**: Best for interactive jobs with multiple users.
- **Single Node Mode**: Best for lightweight processing.

### **c) Optimize Memory and Cores**
- Use **memory-optimized** instances for heavy transformations.
- Ensure **executor memory is balanced** with available cores.



## **3. Optimize Caching & Partitioning**
### **a) Use `.cache()` and `.persist()` Wisely**
- Cache only when you reuse data multiple times.
- Example:
  ```python
  df = df.cache()
  ```

### **b) Optimize Data Partitioning**
- Use **repartition()** for shuffling large datasets:
  ```python
  df = df.repartition(10, "id")
  ```
- Use **coalesce()** to reduce partitions when writing:
  ```python
  df = df.coalesce(4)
  ```



## **4. Optimize Job Execution & Scheduling**
### **a) Use `Photon` for Faster Execution**
- Photon speeds up query execution with C++-based vectorized engine.
- Enable Photon in **Databricks Runtime > 9.1**.

### **b) Optimize Shuffle & Broadcast**
- Reduce **shuffle operations** by avoiding unnecessary aggregations.
- Increase **shuffle partitions** dynamically:
  ```python
  spark.conf.set("spark.sql.shuffle.partitions", "200")
  ```

### **c) Use Checkpoints for Fault Tolerance**
- Avoid large **lineage chains** with checkpoints.
  ```python
  df.write.mode("overwrite").format("delta").save("/tmp/checkpoint")
  ```



## **5. Monitor & Debug Performance**
### **a) Use `Spark UI`**
- Identify **stage bottlenecks**, **shuffle spills**, and **skewed partitions**.

### **b) Enable `Adaptive Query Execution (AQE)`**
- Automatically optimizes queries based on runtime statistics.
  ```python
  spark.conf.set("spark.sql.adaptive.enabled", "true")
  ```

### **c) Enable `Delta Optimizations`**
- Use **OPTIMIZE + ZORDER** for faster Delta queries.
  ```sql
  OPTIMIZE my_table ZORDER BY (id)
  ```