## ETL Challenge

### Which of the following best describes the role of staging tables in an ETL pipeline?
- They store raw data before transformation
- They contain final transformed data ready for reporting
- They replace the need for a data warehouse
- They permanently delete unnecessary records

**Ans:** They store raw data before transformation

**Explanation:**
- In ETL (Extract, Transform, Load), the staging area is an intermediate storage layer where raw data is temporarily stored after extraction but before transformation and loading into the final destination (like a data warehouse).
- Purpose of a Staging Area:
  - Data Cleansing & Validation – Ensures data quality before loading it into the target system.
  - Data Integration – Combines data from multiple sources into a unified format.
  - Performance Optimization – Reduces the load on source systems by allowing bulk processing.
  - Error Handling & Auditing – Provides a place to inspect and correct errors before final loading.
  - Incremental Loading – Stores only new or changed data to optimize processing.