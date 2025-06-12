
# ORDER BY clause
- is used to sort a query by one of its column:
```sql
$	SELECT column_1, column_2 FROM table_name ORDER BY column_name ASC | DESC;
```
- to sort multiple columns:
```sql
$	SELECT column_1, column_2 FROM table_name  ORDER BY column1_name ASC, column2_name DESC;
```
-> ASC : ascending
-> DESC: descending

# WHERE clause
- where is used to filter records that contain specific criteria
-> for numeric values :
```sql
$	SELECT column_1, column_2 FROM table_name WHERE student_id = 01;
```
-> for string values  we should put the string inside quotation:
```sql
$	SELECT clumn1 FROM table_name WHERE  name = 'jaouad';
```
## BETWEEN OPERATOR
- filter records within a numeric or a time range
```sql
$	SELECT column_1 FROM table_name WHERE ID BETWEEN 1 AND 9;
```
```sql
$	SELECT column_1 FROM table_name WHERE date_of_birth BETWEEN '2001-07-01' and '2003-01-02';
```
## LIKE OPERATOR
- used to check string patterns:
```sql
$	SELECT * FROM student_table WHERE faculty LIKE 'Sc%';
```
-> the '%' is used to represent 0 or one or multiple chars
-> the '_' is used to represents 1 char

## IN OPERATOR
- used to select multiple possible values :
```sql
$	SELECT * FROM student_table WHERE country IN('USA', 'UK');
```



# DISTINCT clause
- return only unique values
```sql
$	SELECT DISTINCT country from student_table;
```
- if we use multiples columns we get the different combination of this columns:
```sql
$	SELECT DISTINCT faculty, country FROM student_table;
```