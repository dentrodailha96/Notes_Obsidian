A data lake is a unified analytics platform that combines the best elements of data lakes and data warehouses. Deliver the openness, flexibility and machine learning support of data lakes with the reliability, strong governance and performance of warehouses. 

==Summary:== Single, flexible, high-performance system that supports data, analytics and machine learning workloads. 
### Architecture

» High Level Architecture:

![[Pasted image 20241022162555.png]]

+ Serverless Compute resources run in a serverless compute plane.
+ Classic Databricks compute are cloud services. These clouds are located in Cluster Virutal Machines. 

» Workspace storage bucket:
+ Workspace system data is generated as you use databricks features as notebooks, jobs, commands. 
+ DBFS (Databricks file system): Storing and accessing data using DBFS root or DBFS mounts. 
+ Unity catalog workspace catalog: All users in the workspace can create assets in the default schema in this catalog. 

### Commands
» VACUUM: remove *unused files* from a table directory.
	When vacuum a delta table, it not possible to time travel back to a version older than the specified data retention period. 
	For non-Delta table, recursively vacuums directories associated with non-Delta table and remove uncommitted files older than a retention threshold of 7 days.

» OPTIMIZE: Compacts the small files in large ones to speed the query of a table. 
	Reducing metadata operations, minizing the memory for processes (Disk I/O Overhead), Improving Data Locality and Cache Efficiency (placing related data together), reducing file system limits and fragmentation (concentrating related information) and optimizing data processing in distributed system.  

» PARTITIONED BY: perform an aggregation or window calculation on each partition independently. It's different from PARTITION because it separate directory STRUCTURES. 