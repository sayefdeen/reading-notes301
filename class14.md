# DB Normalization

[Home](https://sayefdeen.github.io/reading-notes301/).

Database normalization is a process used to organize a database into tables and columns. The main idea with this is that a table should be about a specific topic and only supporting topics included.

By limiting a table to one purpose you reduce the number of duplicate data contained within your database. This eliminates some issues stemming from database modifications.

## Reasons for Database Normalization

1. Minimize duplicate data.

2. Minimize or avoid data modification issues.

3. Simplify queries.

## Data Duplication and Modification Anomalies

Duplicated information presents two problems:

- It increases storage and decrease performance.

- It becomes more difficult to maintain data changes.

These situations are modification anomalies. Database normalization fixes them. There are three modification anomalies that can occur:

1. Insert Anomaly : There are facts we cannot record until we know information for the entire row

2. Update Anomaly : having the same information in several rows,If we don’t update all rows, then inconsistencies appear

3. Deletion Anomaly : Deletion of a row causes removal of more than one set of facts

## Various fomrs rules

- **First Normal Form** – The information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns.

- **Second Normal Form** – The table is in first normal form and all the columns depend on the table’s primary key.

- **Third Normal Form** – the table is in second normal form and all of its columns are not transitively dependent on the primary key
