## ETL Challenge: Data Partitioning

### Which partitioning strategy is most effective for time-series data in ETL?
- A) Hash partitioning
- B) Range partitioning
- C) List partitioning
- D) None of the above

**Ans:** B) Range partitioning

**Explanation:**
- Time-series data is inherently sequential and grows over time.
- Range partitioning organizes data based on time intervals (e.g., daily, monthly, yearly), making queries and ETL processes more efficient.
- It allows pruning, meaning queries scan only relevant partitions, improving performance.

- Why Not Others?
  - A) Hash partitioning ❌ – Distributes data randomly, not ideal for time-based queries.
  - C) List partitioning ❌ – Used for categorical values, not continuous time-based data.
  - D) None of the above ❌ – Range partitioning is effective, so this is incorrect.