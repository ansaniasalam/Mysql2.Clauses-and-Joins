# Clauses and Joins

This SQL script contains hands-on exercises on retrieving and analysing data from the employee database. It demonstrates how to filter, sort, group and summarise records, and how to combine data from multiple tables using joins.

## Files

- Schema diagram: [Employee Database Schema](employee-database-schema.png)
- Data insertion script: [Employee Data.sql](Employee%20Data.sql)
- Querying script: [Clauses-and-Joins.sql](Clauses-and-Joins.sql)

The tables were created using the given schema, populated with the data script, and then queried using the script above.

## Concepts Used

### INSERT INTO
Adds rows to a table. The data script uses it to populate the departments, location and employees tables before any queries are run.

### SELECT
Retrieves data from one or more tables. `SELECT *` returns all columns, while naming columns returns only those.

### DISTINCT
Removes duplicate values from the result, so each value appears only once.

### Alias (AS)
Gives a column or table a temporary, readable name in the output. Table aliases such as `e` and `d` also shorten join queries.

### WHERE Clause
Filters rows based on a condition before they are returned.

### Comparison and Logical Operators
Operators such as `>`, `<`, `=`, `AND`, `OR` and `IS NULL` combine and test conditions.

### UPDATE
Modifies existing records. It is used with `WHERE` to fill in a missing designation.

### NULL Handling
`NULL` represents a missing value and must be checked with `IS NULL`, not `=`.

### ORDER BY
Sorts results in ascending (`ASC`) or descending (`DESC`) order. Multiple columns can be sorted together, with later columns breaking ties.

### LIMIT
Restricts the number of rows returned, useful for getting the first few results.

### Date Functions
`YEAR()` extracts the year from a date, so rows can be filtered by hire year.

### Aggregate Functions
Calculate a single value from many rows: `SUM()` for totals, `MIN()` and `MAX()` for extremes, `AVG()` for averages and `COUNT()` for the number of rows.

### GROUP BY
Groups rows with the same value so aggregate functions can be applied to each group separately.

### LIKE and Wildcards
Matches text patterns. `%` stands for any number of characters, so `'%Analyst%'` finds any designation containing "Analyst".

### HAVING
Filters groups after aggregation. It differs from `WHERE`, which filters rows before grouping.

### JOINS
Combine rows from two or more tables using a related column, here the department and location IDs.

### INNER JOIN
Returns only the rows that have matching values in both tables.

### LEFT JOIN
Returns all rows from the left table and the matching rows from the right. Unmatched rows show `NULL`, which makes it useful for including departments with no employees.

### RIGHT JOIN
Returns all rows from the right table and the matching rows from the left. Unmatched rows show `NULL`, which makes it useful for including locations with no employees.

### Comments
`/* */` adds notes to the script to label each query without affecting execution.

## Running the Code

Run the scripts in this order in MySQL Workbench (or any MySQL client):

1. Create the database and tables using the schema.
2. Run `Employee Data.sql` to insert the data.
3. Run `Clauses-and-Joins.sql` to execute the queries.

To run from a terminal instead, use:

```bash
mysql -u root -p < "Employee Data.sql"
mysql -u root -p employee < "Clauses-and-Joins.sql"
```
