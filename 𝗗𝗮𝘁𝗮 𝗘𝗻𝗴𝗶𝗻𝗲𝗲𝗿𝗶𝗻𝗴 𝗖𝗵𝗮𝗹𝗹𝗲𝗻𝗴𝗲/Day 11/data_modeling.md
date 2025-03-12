## Data Modeling Challenge: Data warehousing - Partitioning strategies

### Which partitioning strategy is best for improving query performance in a large sales transactions table?

A) Hash Partitioning
B) Range Partitioning by date
C) Random Partitioning
D) No partitioning at all

**Ans:** B) Range Partitioning by date

**Explanation:**
#### Range Partitioning by Date:
- This is highly effective for time-series data like sales transactions.   
- Sales data is often queried based on date ranges (e.g., "sales for this month," "sales for Q4 2023").   
- Range partitioning by date allows the database to quickly locate the relevant partitions and avoid scanning the entire table, significantly improving query performance.

##### Why Other Options Are Less Effective?
- (A) **Hash Partitioning:** Useful for distributing data evenly but not ideal for time-based queries.
- (C) **Random Partitioning:** Random partitioning distributes data randomly, which is generally not suitable for improving query performance. It offers no logical grouping of data that can be leveraged by queries.
- (D) **No Partitioning at all:** For large tables, querying without partitioning can be very slow, as the database has to scan the entire table to find the relevant data. Partitioning is specifically designed to address this problem.   
   
