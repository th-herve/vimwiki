# Sqlite3

## Start

To start using SQLite3 in a terminal, run the command:

```sql
sqlite3 <database name>.db
```
This will create a new database if the specified name does not already exist.

## Printing schema

```sql
.schema
```

## Importing data from a csv file

Enter csv mode to specify that a csv file will be imported, then import it

```sql
.mode csv

.import <csv name>.csv <table name>
```
# Commands

Here are some useful sqlite3 commands:

* .quit: exits the SQLite3 prompt
* .schema: shows the schema of all tables
* .mode column: changes the display mode to columnar
* .mode table: changes the display mode to tabular
* .timer on: displays the time it takes to execute a query

