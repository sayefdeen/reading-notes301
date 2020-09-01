# SQL DataBase

[Home](https://sayefdeen.github.io/reading-notes301/)

## What is SQL?

SQL, or Structured Query Language, is a language designed to allow both technical and non-technical users query, manipulate, and transform data from a relational database. And due to its simplicity, SQL databases provide safe and scalable storage for millions of websites and mobile applications.

Before learning the SQL syntax, it's important to have a model for what a relational database actually is. A relational database represents a collection of related (two-dimensional) tables. Each of the tables are similar to an Excel spreadsheet, with a fixed number of named columns (the attributes or properties of the table) and any number of rows of data.

## Select Queries.

Query : A query in itself is just a statement which declares what data we are looking for, where to find it in the database, and optionally, how to transform it before it is returned.

To retrive data from a SQL data base, we need to write **SELECT** statment.

**SELECT \* FROM tableName** : this query will select add the columns and rows from the table you have selected.

### Filter Queries

```sql
SELECT coulmn,another_column
FROM table_name
WHERE condition
    AND/OR another_condition
    AND/OR ...;
```

|      Operator       |                                     Condition                                      |          SQL Example          |
| :-----------------: | :--------------------------------------------------------------------------------: | :---------------------------: |
| =, !=, < <=, >, >=  |                            Standard numerical operators                            |         col_name != 4         |
|   BETWEEN … AND …   |                  Number is within range of two values (inclusive)                  | col_name BETWEEN 1.5 AND 10.5 |
| NOT BETWEEN … AND … |                Number is not within range of two values (inclusive)                | col_name NOT BETWEEN 1 AND 10 |
|       IN (…)        |                              Number exists in a list                               |     col_name IN (2, 4, 6)     |
|     NOT IN (…)      |                          Number does not exist in a list                           |   col_name NOT IN (1, 3, 5)   |
|        LIKE         |                      Case insensitive exact string comparison                      |      col_name LIKE "ABC"      |
|      NOT LIKE       |                Case insensitive exact string inequality comparison                 |   col_name NOT LIKE "ABCD"    |
|          %          |     Used anywhere in a string to match characters (only with LIKE or NOT LIKE)     |     col_name LIKE "%AT%"      |
|         \_          | Used anywhere in a string to match a single character (only with LIKE or NOT LIKE) |      col*name LIKE "AN*"      |

**Note :** SQL doesn't require you to write the keywords all capitalized, but as a convention, it helps people distinguish SQL keywords from column and tables names, and makes the query easier to read.

### Filter and Sorting

```sql
SELECt DISTINCT coulnm,another_column,...
FROM table_Name
Where condition(s);
```

DISTINCT : this key word will remove dubpicate rows

```sql
SELECT column,another_column,...
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
```

ORDER BY : this key word will sort rows of any table, alpha-numerically

```sql
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

LIMIT : will reduce the number of rows to return.
OFFSET : will specify where to begin countin the number rows from.

### Rows

Schema : In SQL, the database schema is what describes the structure of each table, and the datatypes that each column of the table can contain.

1. Insert Rows.

```sql
-- This will insert these data in the specific columns
INSERT INTO mytable
(column, another_column, …)
VALUES (value_or_expr, another_value_or_expr, …),
      (value_or_expr_2, another_value_or_expr_2, …),
      …;
```

2. Updating Rows
   The statement works by taking multiple column/value pairs, and applying those changes to each and every row that satisfies the constraint in the WHERE clause.

```sql
UPDATE mytable
SET column = value_or_expr,
    other_column = another_value_or_expr,
    …
WHERE condition;
```

3. Deleting Rows
   When you need to delete data from a table in the database, you can use a DELETE statement, which describes the table to act on, and the rows of the table to delete through the WHERE clause.

```sql
DELETE FROM mytable
WHERE condition;
```

### Tables

Data Types

1. Create tables

```sql
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);
```

2. Altering tables

```sql
-- Adding a new column
ALTER TABLE mytable
ADD column DataType OptionalTableConstraint
    DEFAULT default_value;

-- Removing a coulmn
ALTER TABLE mytable
DROP column_to_be_deleted;

-- Renaming the table
ALTER TABLE mytable
RENAME TO new_table_name;

```

3. Droping table

In some rare cases, you may want to remove an entire table including all of its data and metadata, and to do so, you can use the DROP TABLE statement, which differs from the DELETE statement in that it also removes the table schema from the database entirely.

```sql
DROP TABLE IF EXISTS mytable;
```
