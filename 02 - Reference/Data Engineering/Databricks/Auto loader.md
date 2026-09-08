https://docs.databricks.com/en/ingestion/cloud-object-storage/auto-loader/index.html

+ Auto Loader uses Spark Structured Streaming tool
+ Incrementally and efficiently processes new data files as they arrive in cloud storage without any additional setup. It provides a Structured Streaming source called "CloudFiles".
Code:

	spark.readStream.format(fileFormat).load(directory)

+ You can use Auto Loader to process billions of files to migrate or backfill a table. Auto Loader scales to support near real-time ingestion of millions of files per hour.

» Auto loader Sources: Amazon, Azure Data Lake Storage, Google Cloud Storage, Azure Blob Storage, ADLS, Databricks File System.

» You do not need to provide a schema or checkpoint location because Delta Live Tables automatically manages these settings for your pipelines. Aka.: *"Auto loader monitors a source location, in which files accumulate, to identify and ingest only new arriving files with each command run. While the files that have already been ingested in previous runs are skipped."*

» If added format("cloudFiles), enables to use AutoLoader. 

####  Checkpointing: 
Tracking of files in a specific location. This provides exactly-once ingestion guarantees. Checkpoints allow the system to restart processing from where it left off in case of failure, ensuring reliability.

#### White Ahead Logs: 
Record the description of the operation. This is used when written down into a durable log, and then the operation is applied to the data. In case of failure of the operation, it can recover by reading the log and reapplying the operations it had intended to do. 

#### Idempotent Sink:
Refers to when processing the same data always results in the same outcome. So ideally if a process fails, using checkpointing, it is possible to return to the step and redo all the exactly steps and get the same output. 


