+ Also called ==Data Explorer==
+ UI to manage data, schemas, tables, models etc. The primary functions are finding data assets (find schemas, tables, preview data) and managing unity catalog and delta sharing (grant and revoke permissions of objects).

#### Grant permissions 
![[Pasted image 20241023181955.png]]

![[Pasted image 20241023182025.png]]


### Job permissions
+ Workspace Administrator: typically has the necessary permissions to manage such resources. So if a Data Engineer leave the company, the ownership of him Delta Tables can be transferred by WA.
### Extra commands 

* The `DESCRIBE DATABASE` or `DESCRIBE SCHEMA` returns the metadata of an existing database (schema). The metadata information includes the database’s name, comment, and location on the filesystem. If the optional `EXTENDED` option is specified, database properties are also returned.

* The `USAGE` does not give any abilities, but it's an additional requirement to perform any action on a schema (database) object.
