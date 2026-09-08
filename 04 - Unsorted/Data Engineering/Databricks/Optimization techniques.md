+ Cost definitions.

#### Issues 
+ When a table has too many underlying tiny files, read latency suffers as a result of the time spent for just opening and closing those files. Files between 16MB and 1GB.

### Delta tables compaction features

Spark commands that support Delta tables compaction. 

* Optimize + ZORDER : Compacts the file to get a size of up to 1GB. In other words, compacts the files with the size of the choice and when using ZORDER, reorganize the order of the columns by choice. 

+ Auto optimize: automatically compacts small files during individual writes to a Delta table.

+ Partitioning: can speed up the query if provide the partition columns as filters or join on partition columns or aggregate on partition columns or merge on partition column. 

+ File size tuning: process of adjusting a file's size to meet specific requirements, often balancing between quality and storage limitations. 