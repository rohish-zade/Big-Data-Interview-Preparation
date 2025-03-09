## ETL Challenge: ETL Performance optimization

### Which technique helps speed up ETL processing?

- A) Using indexes
- B) Partitioning large datasets
- C) Avoiding full table scans
- D) All of the above 

**Ans:** D) All of the above

**Explanation:**

Each of these techniques helps improve ETL processing performance:

- A) Using indexes: Indexes can speed up data retrieval by allowing the database to quickly locate rows instead of scanning the entire table. However, indexes should be used carefully in ETL workflows, as they can slow down insert/update operations.
- B) Partitioning large datasets: Partitioning divides large datasets into smaller, more manageable pieces, improving query performance and parallel processing during ETL operations.
- C) Avoiding full table scans: Reducing full table scans minimizes unnecessary reads and speeds up data processing. Strategies include using indexes, partition pruning, and filtering data effectively.