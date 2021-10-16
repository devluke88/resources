# Basics

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

####  LEFT OUTER JOIN

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
