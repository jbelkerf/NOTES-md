# BASIC SQL SYNTAX

## <span style="color:blue">DDL data definition language</span>
### create a database
- to create a table use :
```sql 
$	CREATE DATABASE database_name; 
```
- to create a table use :
```sql
$	CREATE TABLE  table_name;
```
- to  remove a table use
```sql
$	DROP  TABLE  table_name;  
```
- to add a column in a table use:
```sql
$	ALTER TABLE table_name ADD (column_name datatype(size));
```
- to add a [primary key](#primary-key) to a table use :
```sql
$	ALTER TABLE table_name ADD primary key (column_name)
```
- to truncate a table ; empty the table without delete the table itself:
```sql
$	TRUNCATE TABLE table_name;
```
-  to add command to sql use :
```sql
$	--this is a comment
```





## <span style="color:blue"> DML Data Manipulation Language </span>
### inserting to a database
- to insert to a table use : 
```sql
$	INSERT INTO table_name (column_one, column_two...) VALUES (value_one, value_two);
```
### update or modify or delete
- to update an existing data use :
```sql
$	UPDATE table_name SET column_name = value WHERE column_name = value;
```
-  to delete from data use:
```sql
$	DELETE FROM table_name  WHERE column_name = value
```



## <span style="color:blue"> DQL data query language </span>
- to read from database use:
```sql
SELECT column_name , column_name FROM table_name WHERE column_name = value;
```




## <span style="color:blue"> DCL : data control language </span>

### GRANT 
Command to provide the user of the database with the privileges required to allow users to access and manipulate the database.
### REVOKE
Command to remove permissions from any user.





## <span style="color:blue"> TCL transaction control language</span>
### COMMIT
Command to save all the work you have already done in the database.
### ROLLBACK
Command to restore a database to the last committed state.












## primary-key
the primary key is a unique use to differ between columns in a relational database