# Basics

### Create Database

```
CREATE DATABASE tutorial;
```

### Access Database

```
# Login to database (-u username, -p authenticate with password)
mysql -u root -p 
# Enter Password: **********

# You can also login
sudo mysql
```

### Backup Database

```
# Login to database
sudo mysql

# Create a new database
mysql > CREATE DATABASE tutorial_backup;

# Exit mysql with exit command and export table tutorial into a file
mysqldump -u root -p tutorial > tutorial.sql
# Enter Password: **********

# Import the tutorial table into a backup table, for example tutorial_backup
mysql -u root -p tutorial_backup < tutorial.sql
# Enter Password: **********
```

### Create Table

```
CREATE TABLE service (id INTEGER PRIMARY KEY, name TEXT);
```

### Insert Data Into Table

```
INSERT INTO service (id, name) 
  VALUES
(1, 'metor'),
(2, 'silos'),
(3, 'rectan')
(4, 'belkar');
```

### Deleting Data

```
DELETE FROM services WHERE id = 3;
```

### Updating Data

```
UPDATE services SET name = 'meteor' WHERE id = 1;
```

### Example Query

```
SELECT DISTINCT column, AGG_FUNC(column_or_expression), …
FROM mytable
    JOIN another_table
      ON mytable.column = another_table.column
    WHERE constraint_expression
    GROUP BY column
    HAVING constraint_expression
    ORDER BY column ASC/DESC
    LIMIT count OFFSET COUNT;
```

### Aggregate Function

* COUNT(\*), COUNT(column)
* MIN(column)
* MAX(COLUMNS)
* AVG(column)
* SUM(column)

### SQL Joins

#### INNER JOIN

Produces the set of records that match in both table1 and table2 (matching part of both tables).

```
SELECT * FROM table1
INNER JOIN table2
ON table1.name = table2.name;
```

#### FULL OUTER JOIN

Produces the set of records in table1 and table2, that matches records from both tables (all records from both tables, null value if there is no record in one of them).

```
SELECT * FROM table1
FULL OUTER JOIN table2
ON table1.name = table2.name;
```

#### &#x20;LEFT OUTER JOIN

Produces a set of records from table1 + matching records in table2 (full table 1 + common part with table 2, null values if there is no record in table 2).

```
SELECT * FROM table1
LEFT OUTER JOIN table2
ON table1.name = table2.name;
```

If you want just records from table1 without the matching part with table2 (without null values) you can use the following query:

```
SELECT * FROM table1
LEFT OUTER JOIN table2
ON table1.name = table2.name
WHERE table2.id IS null;
```

On the other hand, if you need both tables records but no matching part you can use:

```
SELECT * FROM table1
FULL OUTER JOIN table2
ON table1.name = table2.name
WHERE table1.id IS null
OR table2.id IS null;
```
