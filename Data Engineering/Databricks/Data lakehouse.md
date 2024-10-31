A data lake is a unified analytics platform that combines the best elements of data lakes and data warehouses. Deliver the openness, flexibility and machine learning support of data lakes with the reliability, strong governance and performance of warehouses. 

==Summary:== Single, flexible, high-performance system that supports data, analytics and machine learning workloads. 
### Architecture

» High Level Architecture:

![[Pasted image 20241030085906.png]]

+ Serverless Compute resources run in a serverless compute plane.
+ Classic Databricks compute are cloud services. *These clouds are located in Cluster Virutal Machines.* 
+ The cluster virtual machines and storage are located in customer's cloud account. 
![[lakehouse_platform]]

» The storage account hosting the customer data is provisioned in the data plane in the Databricks customer's cloud account.

» Workspace storage bucket (computer plane - data processing):
+ Workspace system data is generated as you use databricks features as notebooks, jobs, commands. 
+ DBFS (Databricks file system): Storing and accessing data using DBFS root or DBFS mounts. 
+ Unity catalog workspace catalog: All users in the workspace can create assets in the default schema in this catalog. 

#### Data Lakehouse improvements over Data Lake 
One of the key features of a data lakehouse that results in improved data quality over a traditional data lake is its support for ACID (Atomicity, Consistency, Isolation, Durability) transactions. ACID transactions provide data integrity and consistency guarantees, ensuring that operations on the data are reliable and that data is not left in an inconsistent state due to failures or concurrent access.
### Commands
» VACUUM: remove *unused files* from a table directory.
	When vacuum a delta table, it not possible to time travel back to a version older than the specified data retention period. 
	For non-Delta table, recursively vacuums directories associated with non-Delta table and remove uncommitted files older than a retention threshold of 7 days.

» OPTIMIZE: Compacts the small files in large ones to speed the query of a table. 
	Reducing metadata operations, minizing the memory for processes (Disk I/O Overhead), Improving Data Locality and Cache Efficiency (placing related data together), reducing file system limits and fragmentation (concentrating related information) and optimizing data processing in distributed system.  

» PARTITIONED BY: perform an aggregation or window calculation on each partition independently. It's different from PARTITION because it separate directory STRUCTURES. 