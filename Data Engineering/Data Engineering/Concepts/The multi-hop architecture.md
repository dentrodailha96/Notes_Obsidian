+ Delta warehouse organization based on layers (Bronze, Silver, Gold).
+ Also called medallion architecture.
+ Uses the concept of [[Data Mesh]].

![[Pasted image 20241002121506.png]]

+ Allows to load streaming and batch data into one.
+ Implements ETL process in cloud using fast processing and memory optimization techniques. 
+ Change Data Capture.
+ Better data management and security features at each layer. 
+ User level access at different layers.

#### Pre Landing: 
+ Raw form 
+ Data collect from different sources and in parquet format.

#### Bronze Layer: 
+ Data pre processing layer, null check, duplication, data format.
+ Latest data from the source (either full or incremental).

#### Silver Layer:
+ Combine the just landed data by merge queries. 

#### Gold Layer:
+ Aggregation and extra calculation based on the requirements. 