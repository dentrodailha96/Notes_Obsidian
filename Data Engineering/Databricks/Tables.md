### External Tables

» Tables whose data is stored in an external storage path by using a LOCATION clause. When you run "DROP TABLE" on an external table, only the table's metadata is deleted, while the underlying data files are kept.

### Managed tables

Are tables whose metadata and the data are managed by Databricks. When you run DROP TABLE on a managed table, both the metadata and the underlying data files are deleted. 

### Delta table
+ Delta lake is integrated with Spark Structured Streaming through readStream and whiteStream. 
+ Table format that uses Delta Lake to store trustful data with ACID transactions, schema enforcement, time travel, and other features. It's essentially a data type stored in Delta Lake format. 

» SOURCE: While a streaming query is active against a Delta table, new records are processed idempotently as new table versions commit to the source table.

### Delta Live Tables

» CONCEPT: ==Declarative ETL== framework for building reliable, maintainable and testable data processing pipelines. Define streaming tables and materialize views that the system should create and keep up to date. 
	==AKA.: Manages how your data is transformed based on queries you define for each processing step.==

Works on top of Delta Tables. 

» DTL Datasets:
+ Streaming table: Each record is processed exactly once. Append-only source. Streaming tables are optimal for pipelines that require data freshness and low latency (minimal delay). Streaming tables can also be useful for massive scale transformations, as results can be incrementally calculated as new data arrives, keeping results up to date without needing to fully recompute all source data with each update.
+ Materialized views: processed data with expected results from the dataset. It will run transformations, aggregations or pre-computing slow queries and frequently used computations. This view makes possible to store the result of a query and update it time to time, avoiding to run the query every time that is needed. 
+ Views: Records are processed when the query runs, usually used for data checks. Delta Live Tables does not publish views to the catalog, so views can be referenced only within the pipeline in which they are defined.

» Change Data Capture (CDC): this simplifies changes, it is logged at the source as events that contains both the data of the records along with metadata information: 
+ Operation column indicating weather the specified record was inserted, updated or deleted
+ Sequence column that is usually a timestamp indicating the order in which changes happens. 

==You can use the `APPLY CHANGES INTO` statement to use Delta Live Tables CDC functionality==

+ The `APPLY CHANGES` API is supported in the Delta Live Tables SQL and Python interfaces. The `APPLY CHANGES FROM SNAPSHOT` API is supported in the Delta Live Tables Python interface.

» Pipelines: 
+ Require declare a target schema to publish to the Hive metastore or a target catalog and target schema to publish to Unity Catalog. 
+ ==Pipeline page== provides information regarding dropped record, violations of expectation and other data quality metrics. 

» [[Triggers]] pipelines update each table with whatever data is currently available and then they shut down. 
+ In Development mode the development process is eased by reusing a cluster to avoid the overhead of restarts, and *the cluster runs for two hours when the development mode is enabled.* Also, allows disabling pipeline retries so you can immediately detect and fix errors.  
+ In Production mode the terminates the cluster immediately when the pipeline is stopped, restarts the cluster for recoverable errors, retries execution in case of specific errors. *Once an update is started, it continues to run until the pipeline is shut down.*

» QUERIES:
	Query an existing streaming table events:
	
	spark.readStream.table("events")

+ CREATE TABLE: In DLT pipelines, we use the `**CREATE LIVE TABLE**` syntax to create a table with SQL. To query another live table, prepend the `**LIVE.**` keyword to the table name.

![[Pasted image 20241023153327.png]]

* CREATE STREAMING LIVE TABLE: stream data from other tables in the same pipeline by using STREAM(LIVE.).
![[Pasted image 20241028102852.png]]

» Expectations are optional clauses you add to DLT dataset declarations that apply data quality check on each record passing through a query.

An expectation consists of three things:

- A description, which acts as a unique identifier and allows you to track metrics for the constraint.
- A boolean statement that always returns true or false based on some stated condition.
- An action to take when a record fails the expectation, meaning the boolean returns false.

+ ON VIOLATION DROP ROW: Feature available in DLT where you can check the quality of  your dataset at the time of your load to target table and take action like dropping those invalid record that did not meet your conditions making the job fail. 
+ `ON VIOLATION FAIL UPDATE`, records that violate the expectation will cause the pipeline to fail. When a pipeline fails because of an expectation violation, you must fix the pipeline code to handle the invalid data correctly before re-running the pipeline.
+  ==CONTRAINS: By default, records violating the constraint will be kept, and reported as invalid in the event log.==

» LIMITATIONS: 
+ All DLT are Delta Tables
+ can only be defined once, meaning they can only be target of a single operation in all DLT.
+ Identity Columns are not supported with tales that are target of "apply changes into" an might be recomputed during updates or materialized views. 

### Delta Tables vs. Delta Live Tables 

![[Pasted image 20241031085529.png]]
