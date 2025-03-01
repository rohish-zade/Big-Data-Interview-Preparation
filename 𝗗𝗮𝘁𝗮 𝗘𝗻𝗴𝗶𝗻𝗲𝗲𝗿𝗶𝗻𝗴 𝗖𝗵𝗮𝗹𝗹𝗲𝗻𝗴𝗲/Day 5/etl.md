## ETL Challenge: Change Data Capture(CDC)

###  Which technique is commonly used for real-time change tracking in ETL?
- A) Full table scans
- B) Incremental loading
- C) Log-based CDC
- D) Batch processing

**Ans:** Log-based CDC.

**Explanation:**
- `Log-based CDC (Change Data Capture):` This technique captures changes made to the source database by reading and analyzing the database transaction logs. This allows for near real-time tracking of changes as they happen, making it ideal for real-time ETL pipelines.
- ***Here's why the other options are not the best fit for real-time change tracking:***
  - `Full table scans:` This method requires scanning the entire source table to identify changes, which can be very inefficient and time-consuming, especially for large tables.
  - `Incremental loading:` This technique only loads new or updated records since the last ETL run. While more efficient than full table scans, it might not capture changes in real-time.
  - `Batch processing:` This involves processing data in batches at scheduled intervals. It's not suitable for real-time tracking as changes are only captured periodically.