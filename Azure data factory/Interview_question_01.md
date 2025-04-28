### Q1. If you have multiple files with different format(csv/json/txt/parquet) in ADLS. How will you get only csv files?

**Aproch 1: Use Wildcard Filters in the Dataset**
- When you create a Dataset in ADF (for ADLS Gen2): 
  - In the file path setting, use wildcards like: *.csv
  - This tells ADF to only pick files ending with .csv.
- During Copy Activity → Source Settings, If you're using a Copy Activity:
  - In the Source tab → select the dataset you created (with *.csv filter).
  - Set Recursively to true if you want ADF to search inside subfolders.
  - Enable Wildcard Paths like /yourfolder/**/*.csv if needed.

**Alternate Option (if complex logic needed):**
- You can use a Get Metadata Activity to list all files.
- Then use a Filter Activity inside a pipeline:
  - Filter only files that end with .csv using expressions.
- After that, loop over the filtered list (using ForEach activity) to process only the CSVs.


### Q1. How will you migrate RDBMS tables to datalake?

#### 1. Create Linked Services
- Source: RDBMS (SQL Server, Oracle, MySQL, etc.)
- Sink: Azure Data Lake Storage Gen2 (ADLS)

#### 2. Create Datasets
- Source Dataset: RDBMS table or SQL query.
- Sink Dataset: ADLS folder (file format: Parquet preferred).

#### 3. Build Pipeline
- Add Copy Activity.
- Source: Select RDBMS dataset.
- Sink: Select ADLS dataset.
- File format: Parquet or CSV.
- Set Mapping: Auto or manual if needed.

#### 4. Handle Load Types
- Full Load: Copy entire table.
- Incremental Load: Use `LastModifiedDate` or CDC (Change Data Capture).
  - Dynamic query based on watermark timestamp.

#### 5. Optimize Copy Performance
- Enable Parallel Copy for large tables.
- Use Staging if necessary (for large volumes).
- Enable Fault Tolerance settings.

#### 6. Trigger Pipeline
- Manual Trigger (for initial load).
- Scheduled Trigger (for recurring loads - daily/hourly).

#### 7. Best Practices
- Prefer Parquet format (compressed, schema, faster).
- Organize folders by table/date for easy partitioning.
- Monitor and validate data (row count, sample checks).

If your RDBMS tables is in On-Prem then need to create Self-hosted Integration Runtime.

