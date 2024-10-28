* Delta Lake is built on top of Apache Spark in order to allow multiples readers and writes of a given table to all work on the table at the same time. To promote this, uses "logs", repositories that tracks all changes that users makes to the table. 

### Transaction Log

* All ACID actions are recorded in the transaction log as ordered, atomicity (one action at the time).
* When a user creates a Delta Lake table, that table’s transaction log is automatically created in the `**_delta_log**` subdirectory. Each commit is written out as a JSON file.

![[Pasted image 20241028090247.png]]

* Delta Lake is the optimized storage layer that provides the foundation for tables in lakehouse.

![[Pasted image 20240930115458.png]]
![[Pasted image 20240930115602.png]]



