* Python, SQL, Scala and R 
* Coding environments allowing you to interactively developing and executing code on databricks.
* It's possible to create a collaboration (more than one person developing).
* Magic Command are built in commands that provide the same output regardless of the notebook language. 
* Create: Workspace -> Create notebook (it's possible to create a folder to create a notebook)
* %run: runs notebooks in other notebooks. You can override the default language in a cell by using the language magic command at the beginning of a cell. The supported magic commands are: `%python`, `%sql`, `%scala`, and `%r`.
* They have build in version control, but also there is the [[Databricks Repo]].


### SQL 

+ A view in databricks is a virtual table that has no physical data. A SQL query against the actual tables.
+ Temporary view are visible only to the session that created them and dropped when the session ends. 
+ Global Temporary view that can be accessed in other sessions on the same cluster. They are temporary tied to the cluster: global_temp

» Query databases using JDBC:
https://learn.microsoft.com/en-us/azure/databricks/connect/external-systems/jdbc
+ JDBC allows connect to the external databases.
+ DATA_SOURCE: `data_source` can be either a file-format or a federated JDBC data source.

![[Pasted image 20241022123529.png]]

» WAREHOUSE:
+ Workspace admin or user with unrestricted cluster creation permissions.
![[Pasted image 20241023153717.png]]
 + Auto Stop feature stops the warehouse if it's idle for a specified number of minutes. 
+ SQL Warehouse is the resource to compute SQL queries and managing data workload in Databricks. 
+ Characteristics: Elasticity, Dedicated Compute, Concurrency, Caching, Query Optimization.

» CREATE TABLE: 
 + EXTERNAL TABLE: when creating an external table you must also provide a location clause. AND when it is dropped, the files at the location will NOT BE dropped. 
 + Support adding descriptive comment for the table:
![[Pasted image 20241022124111.png]]

» MERGE INTO: merge a set of updates, insertions, and deletions based on a source table into a target Delta table. *Avoiding inserting the duplicate records when writing into Delta Tables.*

» CREATE SCHEMA: creating a database with no specific location clause, the database will be created in the warehouse directory "dbfs:/user/hive/warehouse".

» FILTER structure: 

 filter(input_array, lamda_function)

It is a higher order function that returns an output array from an input array by extracting elements for which the predicate of a lambda function holds.

### Python 
» CREATE FUNCTION (UDF): 

![[Pasted image 20241022154554.png]]

