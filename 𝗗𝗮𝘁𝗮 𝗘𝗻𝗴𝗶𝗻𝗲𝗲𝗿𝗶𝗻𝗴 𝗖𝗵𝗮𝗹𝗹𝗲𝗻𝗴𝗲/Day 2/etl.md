## ETL Challenge

### What is the best way to remove duplicates from a dataset before loading it into a data warehouse?
- Use DISTINCT in SQL queries
- Apply a GROUP BY operation with aggregation
- Deduplicate at the source system before ingestion
- All of the above

**Ans:** All of the above 

**Explanation:**
- Deduplication should happen at multiple stages of the data pipeline.
- DISTINCT in SQL removes duplicates in queries but doesn’t prevent duplicate ingestion.
- GROUP BY with aggregation helps in scenarios where duplicates must be merged based on business logic.
- The best practice is to deduplicate at the source (if possible) to prevent storing unnecessary duplicates.