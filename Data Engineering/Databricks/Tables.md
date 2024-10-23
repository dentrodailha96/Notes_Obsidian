### External Tables

» Tables whose data is stored in an external storage path by using a LOCATION clause. When you run "DROP TABLE" on an external table, only the table's metadata is deleted, while the underlying data files are kept.

### Delta table
+ Delta lake is integrated with Spark Structured Streaming through readStream and whiteStream. 

» SOURCE: While a streaming query is active against a Delta table, new records are processed idempotently as new table versions commit to the source table.


### Delta Live Tables

» CONCEPT: Declarative framework for building reliable, maintainable and testable data processing pipelines. Define streaming tables and materialize views that the system should create and keep up to date. 
	==AKA.: Manages how your data is transformed based on queries you define for each processing step.==

» DTL Datasets:
+ Streaming table: Each record is processed exactly once. Append-only source. Streaming tables are optimal for pipelines that require data freshness and low latency (minimal delay). Streaming tables can also be useful for massive scale transformations, as results can be incrementally calculated as new data arrives, keeping results up to date without needing to fully recompute all source data with each update.
+ Materialized views: processed data with expected results from the dataset. It will run transformations, aggregations or pre-computing slow queries and frequently used computations. This view makes possible to store the result of a query and update it time to time, avoiding to run the query every time that is needed. 
+ Views: Records are processed when the query runs, usually used for data checks. Delta Live Tables does not publish views to the catalog, so views can be referenced only within the pipeline in which they are defined.

» Pipelines: 
+ Require declare a target schema to publish to the Hive metastore or a target catalog and target schema to publish to Unity Catalog. 

» Triggers pipelines update each table with whatever data is currently available and then they shut down. 
+ In Development mode the development process is eased by reusing a cluster to avoid the overhead of restarts, and *the cluster runs for two hours when the development mode is enabled.* 
+ In Production mode the terminates the cluster immediately when the pipeline is stopped, restarts the cluster for recoverable errors, retries execution in case of specific errors. *Once an update is started, it continues to run until the pipeline is shut down.*

» QUERIES:
	Query an existing streaming table events:
	
	spark.readStream.table("events")

+ CREATE TABLE: In DLT pipelines, we use the `**CREATE LIVE TABLE**` syntax to create a table with SQL. To query another live table, prepend the `**LIVE.**` keyword to the table name.

![[Pasted image 20241023153327.png]]



» Expectations are optional clauses you add to DLT dataset declarations that apply data quality check on each record passing through a query.

An expectation consists of three things:

- A description, which acts as a unique identifier and allows you to track metrics for the constraint.
- A boolean statement that always returns true or false based on some stated condition.
- An action to take when a record fails the expectation, meaning the boolean returns false.

+ ON VIOLATION DROP ROW: Feature available in DLT where you can check the quality of  your dataset at the time of your load to target table and take action like dropping those invalid record that did not meet your conditions making the job fail. 
+  ==CONTRAINS: By default, records violating the constraint will be kept, and reported as invalid in the event log.==

» LIMITATIONS: 
+ All DLT are Delta Tables
+ can only be defined once, meaning they can only be target of a single operation in all DLT.
+ Identity Columns are not supported with tales that are target of "apply changes into" an might be recomputed during updates or materialized views. 