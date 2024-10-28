* ==Centralized== access control auditing, lineage and data discovery capabilities across Databricks workspaces.

![[Pasted image 20241024113652.png]]

* Centralized place to admin all data access, which records user-level audit that records the data. Besides, it allows the data assets documentation and provides a UI to the final user. 

![[Unity Catalog Object Model]]
+ Metadata is registered in Metastore (container).
+ Then divided in three-level namespace: catalog.schema.table-etc

## Privileges and securable objects 
* A privilege is a right granted to a [principal](https://docs.databricks.com/en/sql/language-manual/sql-ref-principal.html) to operate on a [securable object](https://docs.databricks.com/en/sql/language-manual/sql-ref-privileges.html#securable-objects) in the metastore.
* Through Unity Catalog it's possible to ==grant and revoke== access to securable objects at any level in the hierarchy, including the metastore itself. 

>> Usage privilege: controlling access to resources and ensuring that only authorized users can view or manage different parts of the Databricks environment.
>> [[Catalog Explorer]]
>Workspace Permissions
>Cluster Permissions 
>Job Permissions 
>Table/SQL Permissions 
>Groups or role-based access control

### Data Explorer
* change the owner field of the table, schema etc. 




