https://docs.databricks.com/en/ingestion/cloud-object-storage/auto-loader/index.html

+ Incrementally and efficiently processes new data files as they arrive in cloud storage without any additional setup. It provides a Structured Streaming source called "CloudFiles".
Code:

	spark.readStream.format(fileFormat).load(directory)

+ You can use Auto Loader to process billions of files to migrate or backfill a table. Auto Loader scales to support near real-time ingestion of millions of files per hour.

» Auto loader Sources: Amazon, Azure Data Lake Storage, Google Cloud Storage, Azure Blob Storage, ADLS, Databricks File System.

» You do not need to provide a schema or checkpoint location because Delta Live Tables automatically manages these settings for your pipelines. Aka.: *"Auto loader monitors a source location, in which files accumulate, to identify and ingest only new arriving files with each command run. While the files that have already been ingested in previous runs are skipped."*
