+ Open-source distributed big data processing engine. 
+ APIs in Java, Scala, Python and R. 

#### Components
![[Pasted image 20240930122105.png]]

Libraries: 

* SQL: SQLquery process.
* Spark Streaming: real-time straming.
* MLLIB: Machine Learning.
* GraphX: Distributed graph computation on top of the Spark core. 

Cluster Managers:

+ Standalone: It is a simples cluster manager which is easier to set up and execute the tasks on the cluster. It is a reliable cluster manager which can handle failures successfully. It can manage the resources based on the application requirement. 
+ Apache Mesos: Runs Hadoop MapReduce with Spark and others. Run the most languages. 
+ Hadoop YARN: It is also a general-purpose cluster manager and can work in both Hadoop and Spark.

### Architecture
![[Pasted image 20240930124709.png]]

### Commands 

»» `spark.table()` function returns the specified Spark SQL table as a PySpark DataFrame.
