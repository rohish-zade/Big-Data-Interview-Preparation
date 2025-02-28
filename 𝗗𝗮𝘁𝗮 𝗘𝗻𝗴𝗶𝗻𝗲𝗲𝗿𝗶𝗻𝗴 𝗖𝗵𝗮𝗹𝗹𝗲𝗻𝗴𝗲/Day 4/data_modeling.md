## Data Modeling Challenge: Star Schema vs Snowflake Schema

### Which schema type generally provides better query performance in analytics?
- A) Star Schema
- B) Snowflake Schema
- C) Both are identical
- D) Neither

**Ans:** Star Schema

**Explanation:**
- `Star Schema:`
  - It has a single fact table surrounded by dimension tables.   
  - This simpler structure generally leads to fewer joins, resulting in faster query performance.   
  - It is optimized for analytical queries.
- `Snowflake Schema:`
  - It is a variation of the star schema where dimension tables are normalized, creating a more complex structure.   
  - While it reduces data redundancy, it requires more joins, which can slow down query performance
  

   
