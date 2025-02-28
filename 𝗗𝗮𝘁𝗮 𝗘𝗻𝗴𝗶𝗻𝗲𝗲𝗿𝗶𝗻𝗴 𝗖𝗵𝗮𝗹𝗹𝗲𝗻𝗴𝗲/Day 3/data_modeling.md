## Data Modeling Challenge: Slowly Changing Dimensions

### Which technique is best for tracking historical changes in a dimensional table?
- Type 1: Overwriting records
- Type 2: Adding a new row with a timestamp
- Type 3: Storing old and new values in the same row
- All of the above

**Ans:** Type 2: Adding a new row with a timestamp

**Explanation:**
- **Type 2 Slowly Changing Dimensions (SCDs):**
  - This method adds a new row to the dimension table whenever a change occurs.
  - Each row is timestamped or has effective and expiration dates, allowing you to track the history of changes over time.
  - This is the most common and effective way to maintain historical data in a data warehouse
- To read more on SCD Types [click here](https://github.com/rohish-zade/Python/blob/master/working_with_databases_and_ETL/scd_types.ipynb)