# Sql select data

To retrieve data from a table, use the following syntax:

```sql
SELECT <column name>, <other column name>, ... 
FROM <table name>;

-- To select every column
SELECT *
FROM <table name>;
```
For example, to select the "name" and "age" column from the "students" table:

```sql
SELECT name, age 
FROM students;
```
