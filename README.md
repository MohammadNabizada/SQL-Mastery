# SQL
SQL: Course Notes &amp; Projects

# 📅 Daily SQL Progress Tracker

## 🌟 About This Journey
Documenting my **45-day challenge** to master SQL through:  
✅ **Daily lesson reviews**  
✅ **Hands-on query practice**  
✅ **Real-world mini projects**  
✅ **Common mistakes & fixes**  


---

## 📚 Course Details
|                  |                                     |
|------------------|-------------------------------------|
| **Course Name**  | [SQL]               |
| **Platform**     | Udemy/Coursera/YouTube              |
| **Instructor**   | [Instructor Name]                   |
| **Tools Used**   |  MySQL Workbench,|
| **My Level**     | Beginner → Intermediate -> advanced |

---
# SQL Concepts Table of Contents

- [Installation and Setup](#installation-and-setup)
- [SELECT Statement](#select-statement)
- [Filtering with WHERE](#filtering-with-where)
- [BETWEEN, LIKE, REGEXP, IS NULL, ORDER BY](#between-like-regexp-is-null-order-by)
- [LIMIT and OFFSET](#limit-and-offset)
- [INNER JOIN](#inner-join)
- [OUTER JOIN](#outer-join)
- [NATURAL JOIN](#natural-join)
- [CROSS JOIN](#cross-join)
- [UNION](#union)
- [INSERT](#insert)
- [UPDATE](#update)
- [DELETE](#delete)
- [Aggregate Functions](#aggregate-functions)
- [GROUP BY and HAVING](#group-by-and-having)
- [WITH ROLLUP](#with-rollup)
- [Subqueries (Scalar)](#subqueries-scalar)
- [IN and NOT IN](#in-and-not-in)
- [ANY and SOME](#any-and-some)
- [ALL](#all)
- [Correlated Subqueries](#correlated-subqueries)
- [EXISTS and NOT EXISTS](#exists-and-not-exists)
- [Subqueries in SELECT Clause](#subqueries-in-select-clause)
- [Derived Tables](#derived-tables)
- [Numerical Functions](#numerical-functions)
- [String Functions](#string-functions)
- [Practical String Application](#practical-string-application)
- [Date/Time Functions](#datetime-functions)
- [Overall Assessment](#overall-assessment)
- [Additional Examples](#additional-examples)
- [Overview](#overview)
- [Numerical Functions](#numerical-functions)
- [String Functions](#string-functions)
- [Practical String Application](#practical-string-application)
- [Date/Time Functions](#datetime-functions)
- [Overall Assessment](#overall-assessment)
- [Additional Examples](#additional-examples)
- [NULL Handling](#null-handling)
- [String Concatenation](#string-concatenation)
- [Conditional Logic](#conditional-logic)
- [Aggregation and Grouping](#aggregation-and-grouping)
- [Views](#views)


## 🗂 Daily Logs
### **Day 1: Install and config MySql**  
📝 **Notes**:  
> "Learning instalation of MYSQL."  

## Installation and Setup
# MySQL 8.0 Installation

*Step 1: Searching MySql downloader, dowanload and install on your computer*




<img width="608" alt="1" src="https://github.com/user-attachments/assets/971f05c6-f087-4c89-a143-3a8505ea8200" />




*Step 2: Selecting MySQL 8.0.41 version and Windows 32-bit installer*



<img width="647" alt="2" src="https://github.com/user-attachments/assets/2cab83c4-7fc1-4bd1-a3d3-a2461f0578f2" />

---



*Step 3: Downloading MySQL Server, Workbench, and related components*



<img width="588" alt="3" src="https://github.com/user-attachments/assets/48cfac0a-1d06-43be-a45e-9c2d76866b06" />

---

*Step 4: Configuring server for development environment*



<img width="587" alt="4" src="https://github.com/user-attachments/assets/d2d9f370-9efb-4129-adae-3d3f620c8382" />

---

*Step 5: Verifying server connection with root credentials*


## Post-Installation
- Verify installation with `mysql --version`
- Launch MySQL Workbench to test connections
- Default port: 3306 (TCP/IP enabled)



## SELECT Statement
### **Day 2: Creating the Databases and SELECT Statement**  
📝 **Notes**:  
> "Database and SELECT Statement" 
## SQL Query Example

This query retrieves all records from  `TABLENAME` table in the `DATABASENAME` database:

```sql
-- Select all columns from the products table
SELECT * FROM DATABASENAME.TABLENAME;

# SQL Query Template

## Basic Query Structure
USE database_name;  -- Sets the active database
SELECT * FROM table_name 
WHERE column_name = 1  -- Filter condition
ORDER BY column_name;  -- Sorting
```

## Command Reference
| Command     | Description                          | Example                  |
|-------------|--------------------------------------|--------------------------|
| `USE`       | Selects the database                 | `USE sql_inventory;`     |
| `SELECT *`  | Retrieves all columns                | `SELECT * FROM products;`|
| `WHERE`     | Filters records                      | `WHERE id = 1`           |
| `ORDER BY`  | Sorts results (ASC by default)       | `ORDER BY price DESC;`   |

## Usage Notes
1. Replace placeholders (`database_name`, `table_name`, etc.) with your actual names
2. For production, specify columns instead of using `SELECT *`
3. The semicolon (`;`) terminates each statement

## Quick Examples
**Connection Test:**
```sql
SELECT 1, 2;  -- Basic connection check
```
## Filtering with WHERE
**Filtered Query:**
```sql
USE shop_db;
SELECT name, price FROM products
WHERE stock > 0
ORDER BY price;
```


### **Day 3: Querying Data with SELECT Statements**

#### **1. Basic Column Selection with Calculation**
```sql
SELECT column1, column2, (column2 * 1.1) AS 'calculated_column'
FROM table
```
- **Purpose**: Retrieve specific columns with a calculated value
- **Key Features**:
  - Explicit column selection (`column1`, `column2`)
  - 10% calculation on `column2`
  - Column aliasing with `AS` for readability
- **Use Case**: Price adjustments, derived metrics

#### **2. Date-Based Filtering (After Specific Date)**
```sql
SELECT *
FROM table
WHERE date_column > 'YYYY-MM-DD'
```
- **Purpose**: Filter records chronologically
- **Key Features**:
  - `*` selects all columns
  - `>` operator for dates after specified date
- **Use Case**: Finding recent transactions, active users

#### **3. Date Range Selection**
```sql
SELECT *
FROM table
WHERE date_column >= 'YYYY-MM-DD'
```
- **Purpose**: Get records from a certain point forward
- **Key Features**:
  - `>=` includes the boundary date
  - Standard ISO date format
- **Use Case**: Fiscal year reporting, anniversary tracking

#### **4. Advanced Conditional Filtering**
```sql
SELECT *
FROM table
WHERE condition1 > 'YYYY-MM-DD' OR 
(condition2 > threshold AND condition3 = 'value')
```
- **Purpose**: Complex record filtering
- **Key Features**:
  - Combined `AND`/`OR` logic
  - Parentheses control evaluation order
- **Use Case**: Targeted marketing, exception reporting

#### **5. Exclusion Filtering**
```sql
SELECT *
FROM table
WHERE column NOT IN ('value1','value2','value3')
```
- **Purpose**: Exclude specific values
- **Key Features**:
  - Clean alternative to multiple `!=` conditions
  - Works with any data type
- **Use Case**: Regional exceptions, category filters

#### **Pro Tips**:
1. Always test date filters with sample data
2. For calculations, consider NULL handling with `COALESCE`
3. Complex conditions benefit from line breaks for readability
4. `NOT IN` performs best with small value lists

> "The SELECT statement is the Swiss Army knife of SQL - master it and you unlock the power of your data." - Database Proverb



## BETWEEN, LIKE, REGEXP, IS NULL, ORDER BY

### **Day 4: BETWEEN, REGEXP, IS NULL, ORDER BY**



# 🐘 SQL Query Snippets — `customers` Table

This repository includes a set of practical SQL queries for selecting, filtering, sorting, and manipulating data from a `customers` table.

These queries are great for learning and practicing SQL basics such as `BETWEEN`, `LIKE`, `REGEXP`, `ORDER BY`, and more.

---


# SQL Query Basics

This guide covers fundamental SQL `SELECT` queries for filtering, pattern matching, sorting, and manipulating data in a database table.

## 1. Filtering with `BETWEEN`
Retrieve rows where a numeric column's value falls within a specified range (inclusive).
```sql
SELECT *
FROM table_name
WHERE column_name BETWEEN 1000 AND 3000;
```

Retrieve rows where a date column falls within a specified date range.
```sql
SELECT *
FROM table_name
WHERE date_column BETWEEN '1990-01-01' AND '2000-01-01';
```

## 2. Pattern Matching with `LIKE`
Filter rows based on string patterns. The `%` wildcard matches any number of characters, and `_` matches a single character.
```sql
SELECT *
FROM table_name
WHERE column_name LIKE '%y'; -- Ends with 'y'
```

```sql
SELECT *
FROM table_name
WHERE column_name LIKE '_____y'; -- Exactly 5 characters before 'y'
```

## 3. Pattern Matching with `REGEXP`
Use regular expressions to match complex string patterns. For example, match strings containing specific characters followed by a particular letter.
```sql
SELECT *
FROM table_name
WHERE column_name REGEXP '[a-c]e'; -- Matches strings with 'ae', 'be', or 'ce'
```
- `^`: Start of string
- `$`: End of string
- `|`: Logical OR
- `[abcd]`: Matches any single character (a, b, c, or d)
- `[a-f]`: Matches any character in the range a to f

## 4. Checking for `NULL` Values
Retrieve rows where a column contains `NULL`.
```sql
SELECT *
FROM table_name
WHERE column_name IS NULL;
```

## 5. Sorting with `ORDER BY`
Sort query results by one or more columns. Use `ASC` (default) for ascending or `DESC` for descending order.
```sql
SELECT *
FROM table_name
ORDER BY column1, column2 DESC; -- Sort by column1 (ASC), then column2 (DESC)
```

Sort by a single column, such as a date.
```sql
SELECT column1, column2
FROM table_name
ORDER BY date_column;
```

## 6. Adding Calculated Columns
Create a constant column with a fixed value in the result set.
```sql
SELECT column1, column2, 10 AS points
FROM table_name
ORDER BY points, column1;
```

## 7. Sorting by Column Position
Refer to columns by their position in the `SELECT` clause (1-based indexing) for sorting.
```sql
SELECT column1, column2, 10 AS points
FROM table_name
ORDER BY 1, 2; -- Sort by column1, then column2
```

## Key Points
- Use `BETWEEN` for range-based filtering (numbers or dates).
- Use `LIKE` for simple string pattern matching and `REGEXP` for advanced patterns.
- Use `IS NULL` to find missing values.
- Use `ORDER BY` to sort results, with optional `ASC`/`DESC` and column position references.
- Add calculated columns with aliases (e.g., `AS points`) for clarity.











## LIMIT and OFFSET

### **Day 5: LIMIT, JOIN**



Here's a polished, generalized version of your SQL query explanations in professional README format:

# SQL Query Patterns Guide

## Query 1: Basic Result Limiting
```sql
SELECT *
FROM table
LIMIT 4
```

### **Purpose**  
Retrieve a controlled subset of records from a dataset

### **Key Features**
- `LIMIT` clause restricts the number of returned rows
- Returns only the first N records (4 in this example)
- Non-destructive operation (preserves original data)

### **Use Cases**
- Data exploration and sampling
- Reducing load on application UIs
- Testing query logic with partial results

### **Performance Notes**
- Significantly reduces memory/bandwidth usage
- Faster response times for large datasets
- More efficient than fetching all rows then filtering client-side

---

## Query 2: Offset Limiting (Pagination)
```sql
SELECT *
FROM table
LIMIT 6,3
```

### **Purpose**  
Implement paginated data retrieval

### **Key Features**
- Two-number syntax: `LIMIT offset, count`
- Skips initial records (6) before returning results (3)
- Standard alternative: `LIMIT 3 OFFSET 6`

### **Use Cases**
- Web/mobile app pagination
- Batch processing of large datasets
- Implementing "Load More" functionality

### **Implementation Notes**
- First value = number of rows to skip
- Second value = number of rows to return
- Combine with `ORDER BY` for consistent pagination

---
## INNER JOIN
## Query 3: Table Join with Column Selection
```sql
SELECT t1.id, t1.foreign_key, t2.field1, t2.field2
FROM table1 t1
JOIN table2 t2
     ON t1.foreign_key = t2.primary_key
```

### **Purpose**  
Combine related data from multiple tables

### **Key Features**
- Explicit column selection (avoids `SELECT *`)
- Table aliases (`t1`, `t2`) improve readability
- `INNER JOIN` returns only matching records
- Join condition specifies relationship

### **Use Cases**
- Generating comprehensive reports
- Combining normalized data
- Creating unified views from multiple sources

### **Best Practices**
1. Always qualify column names in joins
2. Prefer explicit column lists over `*`
3. Use meaningful table aliases
4. Verify join conditions match indexed columns

---

## **Expert Recommendations**

### **Optimization Tips**
- Add indexes on join/where/filter columns
- For pagination, ensure consistent sort order
- Consider CTEs for complex multi-table queries

### **Alternative Approaches**
```sql
-- Modern pagination syntax
SELECT * FROM table
ORDER BY sort_column
LIMIT 3 OFFSET 6;

-- LEFT JOIN to include non-matching rows
SELECT t1.*, t2.optional_field
FROM main_table t1
LEFT JOIN optional_data t2
     ON t1.id = t2.ref_id
```

### **Proverb**  
*"Good SQL is like good writing - clarity comes from precision and structure."*

---

This version:
- Uses neutral table/column names
- Maintains consistent section structure
- Provides actionable best practices
- Includes performance considerations
- Offers alternative syntax examples
- Preserves professional formatting

## OUTER JOIN
### **Day 6: INNER JOIN, OUTER JOIN**

# SQL JOIN Operations Reference

## Core JOIN Patterns

### 1. Basic INNER JOIN
```sql
SELECT *
FROM primary_table pt
JOIN related_table rt ON pt.key_field = rt.foreign_key
```

Purpose: Retrieve only matching records from both tables
Characteristics:

    Most common JOIN type

    Returns only rows satisfying the join condition

    Use for standard relational queries

2. Multi-Table JOIN

```sql SELECT *
FROM table1 t1
JOIN table2 t2 ON t1.key = t2.foreign_key
JOIN table3 t3 ON t2.other_key = t3.relation_key
```

Purpose: Combine data from three or more related tables
Note:

    Chain multiple JOIN clauses

    Table aliases become essential

3. LEFT OUTER JOIN

```sql SELECT *
FROM main_table mt
LEFT JOIN secondary_table st ON mt.id = st.ref_id
```
Purpose: Retrieve all main records plus optional related data
Key Behavior:

    Returns ALL rows from left table

    NULL values for unmatched right table columns

    Essential for "show all with optional details" scenarios

4. RIGHT OUTER JOIN


```sql SELECT *
FROM reference_table rt
RIGHT JOIN primary_table pt ON rt.id = pt.ref_id
```

Purpose: Get all right table records with optional left matches
Note:

    Can usually be rewritten as LEFT JOIN

    Less commonly used than LEFT JOIN

JOIN Comparison Matrix
Operation	Syntax	Returns	Typical Use Case
INNER JOIN	JOIN	Matching rows only	Standard relational queries
LEFT JOIN	LEFT JOIN	All left + matches	Preserve primary records
RIGHT JOIN	RIGHT JOIN	All right + matches	Rare edge cases
FULL JOIN	FULL JOIN	All records from both	Complete relationship analysis
Best Practices

    Always:

```sql -- Use explicit JOIN syntax
SELECT t1.field1, t2.field2
FROM table1 t1
JOIN table2 t2 ON t1.id = t2.t1_id
```
Avoid:
```sql

-- Implicit JOINs (comma syntax)
SELECT * FROM table1, table2 WHERE table1.id = table2.t1_id
```

Optimize:
```sql

-- Filter early in JOIN conditions
SELECT t1.*, t2.*
FROM table1 t1
JOIN table2 t2 ON t1.id = t2.t1_id AND t2.status = 'active'
```

Performance Considerations

Create indexes on join columns

Prefer WHERE filters over HAVING for join results

Limit result sets before joining when possible:

```sql

WITH filtered AS (
  SELECT * FROM large_table WHERE condition LIMIT 100
)
SELECT * FROM filtered JOIN other_table...
```

# SQL JOIN Operations Guide

## 1. Implicit INNER JOIN (Legacy Syntax)
```sql
SELECT *
FROM child_table ct, parent_table pt
WHERE pt.parent_id = ct.foreign_key
```

Purpose: Basic table joining (historical approach)
Characteristics:

    Comma-separated tables in FROM clause

    Join condition in WHERE clause

    Functionally equivalent to INNER JOIN
    Modern Best Practice:


    SELECT *
FROM child_table ct
JOIN parent_table pt ON ct.foreign_key = pt.parent_id

```sql SELECT *
FROM child_table ct
JOIN parent_table pt ON ct.foreign_key = pt.parent_id
```
# SQL JOINs and UNIONs Explained 🗂️

A complete guide to combining data in SQL with practical examples.

## Table of Contents 📑
1. [JOIN Fundamentals](#join-fundamentals-)
2. [JOIN Types Deep Dive](#join-types-deep-dive-)
3. [UNION Operations](#union-operations-)
4. [Performance Considerations](#performance-considerations-⚡)
5. [Cheat Sheet](#cheat-sheet-📋)

---

## JOIN Fundamentals 🔗

### What is a JOIN?
```sql
SELECT t1.column1, t2.column2
FROM table1 t1
JOIN table2 t2 ON t1.key = t2.key
```

    Combines rows from two or more tables

    Matches records based on related columns

    Fundamental for relational database queries

Basic JOIN Types
Type	Description	Visual
INNER	Only matching rows	[🟦]∩[🟨]
LEFT	All left + matching right	[🟦]→[🟨]
RIGHT	All right + matching left	[🟦]←[🟨]
FULL	All rows from both	[🟦]↔[🟨]
CROSS	All combinations	[🟦]×[🟨]
JOIN Types Deep Dive 🔍
1. INNER JOIN (Default JOIN)

```sql
SELECT users.name, orders.total
FROM users
INNER JOIN orders ON users.id = orders.user_id
```

    🔹 Returns only matching rows

    🔹 Most common JOIN type

    🔹 Omits non-matching records

2. LEFT JOIN (LEFT OUTER JOIN)


```sql
SELECT departments.name, employees.count
FROM departments
LEFT JOIN employees ON departments.id = employees.dept_id
```

    🔹 Returns ALL left table rows

    🔹 Includes matching right rows

    🔹 Right side NULLs when no match

```sql
SELECT sizes.name, colors.hex_value
FROM sizes
CROSS JOIN colors
```

4. Self JOIN
```sql
SELECT a.employee, b.manager
FROM staff a
JOIN staff b ON a.manager_id = b.employee_id
```

    🔹 Join table to itself

    🔹 Requires table aliases

    🔹 Common for hierarchies



UNION Operations ⛓️
Basic UNION


```sql
SELECT product FROM current_inventory
UNION
SELECT product FROM discontinued_items

```

    🔹 Stacks results vertically

    🔹 Eliminates duplicate rows

    🔹 Columns must match in type


UNION ALL
```sql
SELECT city FROM offices
UNION ALL
SELECT city FROM warehouses
```


Complex UNION Example
```sql

SELECT id, name, 'active' AS status FROM users WHERE last_login > NOW() - INTERVAL '30 days'
UNION
SELECT id, name, 'inactive' AS status FROM users WHERE last_login <= NOW() - INTERVAL '30 days'

    🔹 Different filters for same table

    🔹 Added status column

    🔹 Combined result set


```

JOIN Optimization Tips

    Index join columns - CREATE INDEX idx_name ON table(join_column)

    Filter early - Apply WHERE clauses before joining

    Limit columns - Select only what you need

    Analyze join order - Smaller tables first

UNION vs. JOIN
Operation	Direction	Duplicates	Typical Use
JOIN	Horizontal	Preserved	Combine related data
UNION	Vertical	Removed*	Stack similar data

*Except with UNION ALL
Cheat Sheet 📋
JOIN Syntax Quick Reference


-- INNER JOIN (standard)
sql``` SELECT * FROM A JOIN B ON A.key = B.key ```

-- LEFT JOIN
sql``` SELECT * FROM A LEFT JOIN B ON A.key = B.key ```


## NATURAL JOIN

## 1. Joining Tables
### NATURAL JOIN
```sql
SELECT 
    t1.id,
    t2.name
FROM table1 t1
NATURAL JOIN table2 t2
```
**Purpose**: Retrieves `id` from the first table and `name` from the second table using a `NATURAL JOIN`.  
**Review**: This query joins two tables based on columns with identical names (e.g., a shared `id`). While concise, `NATURAL JOIN` can be risky in production as it assumes matching column names, which may lead to unintended joins if schemas change. Explicit `JOIN ... ON` syntax is often preferred for clarity and control.

## CROSS JOIN
### CROSS JOIN (Explicit and Implicit)
```sql
SELECT t2.name AS entity, t3.item AS product
FROM table2 t2
CROSS JOIN table3 t3

SELECT t2.name AS entity, t3.item AS product
FROM table2 t2, table3 t3
ORDER BY t2.name
```
**Purpose**: These queries produce a Cartesian product, pairing every row from the second table with every row from the third table. The second query includes an `ORDER BY` to sort results by `name`.  
**Review**: Both snippets achieve the same result, with the first using explicit `CROSS JOIN` syntax and the second using an implicit comma-based join. The explicit syntax is more readable and modern. Adding `ORDER BY` in the second query enhances usability by organizing output. Use `CROSS JOIN` cautiously, as it can generate large result sets.

### CROSS JOIN with Another Table
```sql
SELECT t4.id AS id, t3.item AS product_name
FROM table4 t4
CROSS JOIN table3 t3

SELECT t4.id AS id, t3.item AS product_name
FROM table4 t4, table3 t3
```
**Purpose**: Pairs every `id` from the fourth table with every `item` from the third table.  
**Review**: These snippets mirror the previous `CROSS JOIN`, demonstrating consistency in joining unrelated tables. The aliasing (`id`, `product_name`) improves readability. The explicit `CROSS JOIN` is preferred for clarity, but both are functionally equivalent. Ensure the result set size is manageable in real-world applications.

## UNION
## 2. Combining Data with UNION
### Active and Archived Records
```sql
SELECT id, date, 'Active' AS status
FROM table1
WHERE date >= '2019-01-01'
UNION
SELECT id, date, 'Archived' AS status
FROM table1
WHERE date < '2019-01-01'
```
**Purpose**: Combines two result sets from the first table, labeling records from 2019 or later as "Active" and earlier as "Archived".  
**Review**: The `UNION` operator removes duplicates, ensuring a clean result set. This query is excellent for categorizing data based on a condition (date). Using a constant (`'Active'`, `'Archived'`) as a derived column adds context. Ensure column types match across `UNION` queries to avoid errors.

### Combining Names from Two Tables
```sql
SELECT name
FROM table2
UNION 
SELECT name 
FROM table4
```
**Purpose**: Merges unique `name` values from the second and fourth tables.  
**Review**: This `UNION` combines single-column results, removing duplicates. It’s useful for generating a unified list of names from different entities. Be cautious with column name consistency; renaming one for clarity (e.g., using `AS`) could improve readability.

### Tiered Categorization
```sql
SELECT id, name, score, 'Gold' AS type
FROM table2
WHERE score >= 3000
UNION
SELECT id, name, score, 'Silver' AS type
FROM table2
WHERE score BETWEEN 2000 AND 3000
UNION
SELECT id, name, score, 'Bronze' AS type
FROM table2
WHERE score < 2000
ORDER BY score DESC
```
**Purpose**: Categorizes records into "Gold," "Silver," or "Bronze" tiers based on `score`, sorting results by score in descending order.  
**Review**: This query elegantly segments data using `UNION` and conditions. The `ORDER BY score DESC` applies to the entire result set, making it user-friendly. Descriptive aliases (`type`) enhance readability. Ensure `score` is indexed for performance in large datasets.

## INSERT
## 3. Inserting Data
### Inserting into a Table
```sql
INSERT INTO table2
VALUES (DEFAULT, 'ali', 'nabi', '1990-01-01', NULL, 'address', 'city', 'CA', DEFAULT)

INSERT INTO table2 (first_name, last_name, birth_date, address, city, state)
VALUES ('ali', 'nabi', '1990-01-01', 'address', 'city', 'CA')
```
**Purpose**: Adds a new record to the second table, using both full-column and selective-column `INSERT` statements.  
**Review**: The first query uses `DEFAULT` for auto-generated fields (e.g., `id`), ideal for tables with auto-incrementing keys. The second query explicitly lists columns, which is safer and more maintainable if the schema changes. Both are valid, but the second is preferred for clarity and robustness.

### Inserting Multiple Records
```sql
INSERT INTO table4 (name)
VALUES ('entity1'), ('entity2'), ('entity3')
```
**Purpose**: Inserts three records into the fourth table.  
**Review**: This multi-row `INSERT` is efficient, reducing database round-trips. Specifying only the `name` column is appropriate if other columns have defaults or are nullable. Ensure the `name` column allows unique values if required by the schema.

### Inserting Items
```sql
INSERT INTO table3 (id, name, quantity, price)
VALUES (DEFAULT, 'item1', 230, 1), (DEFAULT, 'item2', 12, 2), (DEFAULT, 'item3', 76, 3)
```
**Purpose**: Adds three items to the third table with specified quantities and prices.  
**Review**: Using `DEFAULT` for `id` supports auto-incrementing primary keys. The multi-row insert is efficient, and the values are well-structured. Consider adding error handling (e.g., checking for duplicate names) in production.

### Inserting Related Records
```sql
INSERT INTO table1 (ref_id, date, status)
VALUES (1, '2019-01-02', 1);
INSERT INTO table5
VALUES (LAST_INSERT_ID(), 1, 1, 2.95), (LAST_INSERT_ID(), 2, 1, 3.95)
```
**Purpose**: Creates a new record in the first table and associates two items with it in a related table, using the generated `id`.  
**Review**: The use of `LAST_INSERT_ID()` ensures items are linked to the new record, maintaining referential integrity. This is a great example of handling parent-child relationships. Ensure `ref_id` exists to avoid foreign key violations.

## 4. Archiving Data
### Creating an Archive Table
```sql
CREATE TABLE table1_archived AS
SELECT * FROM table1

INSERT INTO table1_archived
SELECT * FROM table1
WHERE date < '2019-01-01'
```
**Purpose**: Creates a new archive table with the same structure as the first table and populates it with pre-2019 records.  
**Review**: The `CREATE TABLE ... AS` statement is a concise way to duplicate table structure and data. The subsequent `INSERT` filters for older records, useful for archiving. Be aware that `SELECT *` may include unnecessary columns; explicitly listing columns can improve clarity and performance.

### Creating a Selective Archive
```sql
CREATE TABLE archive_table
SELECT 
    t6.record_id,
    t6.number,
    t7.name AS entity,
    t6.total,
    t6.payment_total,
    t6.record_date,
    t6.payment_date,
    t6.due_date
FROM table6 t6
JOIN table7 t7
USING (shared_id)
WHERE t6.payment_date IS NOT NULL
```
**Purpose**: Creates an archive table with selected columns from two tables, including only records with a payment date.  
**Review**: This query demonstrates practical archiving, joining two tables using the `USING` clause for a shared `id`. Filtering by `payment_date IS NOT NULL` ensures only paid records are archived. Explicitly listing columns (instead of `SELECT *`) is a best practice, improving maintainability and performance.

## Summary
These SQL snippets showcase a range of operations: joining tables, combining result sets, inserting data, and archiving. They are well-structured for learning and demonstration, with clear use of aliases, conditions, and modern syntax. For production use, consider:
- Replacing `NATURAL JOIN` with explicit `JOIN ... ON`.
- Adding indexes for frequently filtered columns (e.g., `date`, `score`).
- Validating foreign keys and unique constraints during inserts.
- Using explicit column lists in `SELECT *` queries for archiving.

This collection is an excellent addition to a GitHub repository, demonstrating proficiency in SQL for data manipulation and management.











-- CROSS JOIN
```sql SELECT * FROM A CROSS JOIN B ```

-- SELF JOIN
```sqlSELECT * FROM TableA a1 JOIN TableA a2 ON a1.key = a2.key```

## UPDATE
# SQL Update Operations Showcase

This project demonstrates various SQL `UPDATE` statements to modify data in the `sql_invoicing` and `sql_store` databases, showcasing practical database management tasks like payment adjustments, loyalty rewards, and customer tagging. Below are the key operations with explanations.

## Code and Explanations

### 1. Update Specific Invoice Payment
```sql
USE sql_invoicing;
UPDATE invoices
SET payment_total = 10, payment_date = '2020-03-01'
WHERE invoice_id = 1;
```
- **Purpose**: Records a $10 payment on March 1, 2020, for invoice ID 1.

### 2. Reset Invoice Payment to Defaults
```sql
USE sql_invoicing;
UPDATE invoices
SET payment_total = DEFAULT, payment_date = DEFAULT
WHERE invoice_id = 1;
```
- **Purpose**: Resets payment fields to default values (e.g., 0 or NULL) for invoice ID 1.

### 3. Adjust Payment for Invoice
```sql
USE sql_invoicing;
UPDATE invoices
SET payment_total = payment_total * 0.5, payment_date = due_date
WHERE invoice_id = 3;
```
- **Purpose**: Halves the payment total and sets the payment date to the due date for invoice ID 3.

### 4. Update Invoices for Specific Clients
```sql
SET SQL_SAFE_UPDATES = 0;
USE sql_invoicing;
UPDATE invoices
SET payment_total = invoice_total * 0.5, payment_date = due_date
WHERE client_id IN (3, 4);
```
- **Purpose**: Applies a 50% payment reduction and aligns payment with due date for clients 3 and 4, after disabling safe mode.

### 5. Reward Loyal Customers
```sql
USE sql_store;
UPDATE customers
SET points = points + 50
WHERE birth_date < '1990-01-01';
```
- **Purpose**: Adds 50 loyalty points to customers born before 1990.

### 6. Regional Invoice Adjustments
```sql
USE sql_invoicing;
UPDATE invoices
SET payment_total = invoice_total * 0.5, payment_date = due_date
WHERE client_id IN (
    SELECT client_id
    FROM clients
    WHERE state IN ('CA', 'NY')
);
```
- **Purpose**: Reduces payment by 50% and sets payment date to due date for clients in CA or NY.

### 7. Tag Gold Customers
```sql
UPDATE orders
SET comments = 'Gold customer'
WHERE customer_id IN (
    SELECT customer_id
    FROM customers
    WHERE points > 3000
);
```
- **Purpose**: Marks orders from customers with over 3000 points as “Gold customer.”





# SQL Code Review

This document provides a detailed review of the provided SQL code, evaluating correctness, clarity, potential issues, and suggestions for improvement. Each query is analyzed separately with corrected versions where applicable.
## DELETE
## DELETE FROM Invoices with Subquery
```sql
DELETE FROM invoices
WHERE client_id = 
(SELECT *
FROM clients 
WHERE name = 'Myworks')
```

### Review
- **Issue**: The subquery `SELECT *` is incorrect because a subquery in a `WHERE` clause with `=` must return a single column and row. Using `SELECT *` returns all columns, causing a syntax error.
- **Potential Risk**: If multiple clients have the name 'Myworks', the subquery could return multiple rows, leading to a runtime error.
- **Clarity**: The intent to delete invoices for a client named 'Myworks' is clear, but the syntax is flawed.
- **Suggestion**:
  - Use `SELECT client_id` instead of `SELECT *` to return only the `client_id` column.
  - Use `IN` instead of `=` to handle multiple matching clients.
  - Add `LIMIT 1` in the subquery if only one client is expected, or verify that `name` is unique in the `clients` table.

### Corrected Code
```sql
DELETE FROM invoices
WHERE client_id IN 
(SELECT client_id
FROM clients 
WHERE name = 'Myworks')
```

## Database Restoration Note
```sql
RESTORING THE DATABASE
```

### Review
- **Issue**: This is not a valid SQL statement, likely a comment or note rather than executable code.
- **Potential Risk**: If intended as a restoration command (e.g., restoring from a backup), it lacks proper syntax (e.g., `RESTORE DATABASE` in SQL Server or `mysql` command for MySQL).
- **Clarity**: The intent is unclear without context, possibly a placeholder for a database restoration process.
- **Suggestion**:
  - Use proper SQL comment syntax (e.g., `--` or `/* */`) if this is a comment.
  - If restoration is intended, provide the correct command for the database system.
  - Example for MySQL:
    ```sql
    -- Restore database (example for MySQL)
    -- mysql -u username -p sql_invoicing < backup.sql
    ```
## Aggregate Functions
## Aggregate Queries on Invoices

### Maximum, Minimum, and Average Invoice Totals
```sql
USE sql_invoicing;
SELECT MAX(invoice_total) AS highest,
       MIN(invoice_total) AS lowest,
       AVG(invoice_total) AS average
FROM invoices
```

#### Review
- **Correctness**: The query correctly calculates the maximum, minimum, and average of `invoice_total` from the `invoices` table.
- **Clarity**: The query is clear and concise, with descriptive column aliases.
- **Potential Issue**: No filtering condition is applied, so it processes all rows, which is fine if intended but may impact performance on large datasets.
- **Suggestion**:
  - Add a `WHERE` clause if analysis should be limited to a specific period or condition.
  - If `invoice_total` can be `NULL`, clarify whether to exclude `NULL` values (e.g., `WHERE invoice_total IS NOT NULL`).

### Detailed Invoice Statistics After July 2019
```sql
USE sql_invoicing;
SELECT MAX(payment_date) AS highest,
       MIN(payment_date) AS lowest,
       AVG(payment_date) AS average,
       SUM(invoice_total) AS total,
       COUNT(invoice_total * 1.1) AS number_of_invoices,
       COUNT(payment_date) AS count_of_payment,
       COUNT(*) AS total_records
FROM invoices
WHERE invoice_date > '2019-07-01'
```

#### Review
- **Issue**: The `AVG(payment_date)` is problematic, as averaging a `DATE` or `DATETIME` column is not meaningful and may cause errors or unexpected results.
- **Correctness**: Other aggregates (`MAX`, `MIN`, `SUM`, `COUNT`) are correct, assuming valid column types.
- **Clarity**: Aliases are descriptive, but `number_of_invoices` for `COUNT(invoice_total * 1.1)` is misleading, as it counts non-`NULL` rows where the calculation is performed, not necessarily invoices.
- **Potential Risk**: `NULL` values in `payment_date` or `invoice_total` may skew `COUNT` results.
- **Suggestion**:
  - Remove `AVG(payment_date)` or replace it with a meaningful metric (e.g., average days between `invoice_date` and `payment_date`).
  - Clarify `COUNT(invoice_total * 1.1)`; use `COUNT(*)` or `COUNT(invoice_id)` for invoice counts.
  - Example correction:
    ```sql
    SELECT MAX(payment_date) AS latest_payment,
           MIN(payment_date) AS earliest_payment,
           SUM(invoice_total) AS total,
           COUNT(*) AS number_of_invoices,
           COUNT(payment_date) AS count_of_payments,
           COUNT(*) AS total_records
    FROM invoices
    WHERE invoice_date > '2019-07-01'
    ```

### Client-Based Invoice Statistics After July 2019
```sql
USE sql_invoicing;
SELECT MAX(payment_date) AS highest,
       MIN(payment_date) AS lowest,
       AVG(payment_date) AS average,
       SUM(invoice_total) AS total,
       COUNT(invoice_total * 1.1) AS number_of_invoices,
       COUNT(payment_date) AS count_of_payment,
       COUNT(DISTINCT client_id) AS total_records
FROM invoices
WHERE invoice_date > '2019-07-01'
```

#### Review
- **Issue**: As before, `AVG(payment_date)` is not meaningful and should be removed or replaced.
- **Difference**: Uses `COUNT(DISTINCT client_id)` for `total_records`, counting unique clients instead of total rows.
- **Clarity**: The alias `total_records` is misleading, as it counts distinct clients, not records.
- **Suggestion**:
  - Rename `total_records` to `distinct_clients` for clarity.
  - Remove `AVG(payment_date)` or replace with a meaningful metric.
  - Example correction:
    ```sql
    SELECT MAX(payment_date) AS latest_payment,
           MIN(payment_date) AS earliest_payment,
           SUM(invoice_total) AS total,
           COUNT(*) AS number_of_invoices,
           COUNT(payment_date) AS count_of_payments,
           COUNT(DISTINCT client_id) AS distinct_clients
    FROM invoices
    WHERE invoice_date > '2019-07-01'
    ```

### Sales and Payments by Half-Year 2019
```sql
USE sql_invoicing;
SELECT 
      'First half of 2019' AS date_range,
      SUM(invoice_total) AS total_sales,
      SUM(payment_total) AS total_payment,
      SUM(invoice_total - payment_total) AS what_we_expected
FROM invoices
WHERE invoice_date BETWEEN '2019-01-01' AND '2019-06-30'
UNION
SELECT 
      'Soccond half of 2019' AS date_range,
      SUM(invoice_total) AS total_sales,
      SUM(payment_total) AS total_payment,
      SUM(invoice_total - payment_total) AS what_we_expected
FROM invoices
WHERE invoice_date BETWEEN '2019-07-01' AND '2019-12-30'
UNION 
SELECT 
      'Total' AS date_range,
      SUM(invoice_total) AS total_sales,
      SUM(payment_total) AS total_payment,
      SUM(invoice_total - payment_total) AS what_we_expected
FROM invoices
WHERE invoice_date BETWEEN '2019-01-01' AND '2019-12-30'
```

#### Review
- **Issue**: Typo in `'Soccond half of 2019'` (should be `'Second half of 2019'`).
- **Correctness**: The query correctly uses `UNION` to combine results for two periods and a total. The `BETWEEN` clause is inclusive, which is appropriate.
- **Clarity**: The alias `what_we_expected` is vague; it likely represents outstanding balances.
- **Potential Risk**: `NULL` values in `invoice_total` or `payment_total` may skew results. Use `COALESCE` to handle `NULLs`.
- **Suggestion**:
  - Fix the typo to `'Second half of 2019'`.
  - Rename `what_we_expected` to `outstanding_balance` for clarity.
  - Use `COALESCE` for `NULL` handling.
  - Example correction:
    ```sql
    USE sql_invoicing;
    SELECT 
          'First half of 2019' AS date_range,
          SUM(COALESCE(invoice_total, 0)) AS total_sales,
          SUM(COALESCE(payment_total, 0)) AS total_payments,
          SUM(COALESCE(invoice_total, 0) - COALESCE(payment_total, 0)) AS outstanding_balance
    FROM invoices
    WHERE invoice_date BETWEEN '2019-01-01' AND '2019-06-30'
    UNION
    SELECT 
          'Second half of 2019' AS date_range,
          SUM(COALESCE(invoice_total, 0)) AS total_sales,
          SUM(COALESCE(payment_total, 0)) AS total_payments,
          SUM(COALESCE(invoice_total, 0) - COALESCE(payment_total, 0)) AS outstanding_balance
    FROM invoices
    WHERE invoice_date BETWEEN '2019-07-01' AND '2019-12-30'
    UNION 
    SELECT 
          'Total' AS date_range,
          SUM(COALESCE(invoice_total, 0)) AS total_sales,
          SUM(COALESCE(payment_total, 0)) AS total_payments,
          SUM(COALESCE(invoice_total, 0) - COALESCE(payment_total, 0)) AS outstanding_balance
    FROM invoices
    WHERE invoice_date BETWEEN '2019-01-01' AND '2019-12-30'
    ```
## GROUP BY and HAVING
## Group By Queries

### Total Sales by State and City
```sql
SELECT 
   state,
   city,
   SUM(invoice_total) AS total_sales
FROM invoices i
JOIN clients USING(client_id)
GROUP BY state, city
```

#### Review
- **Correctness**: The query correctly joins `invoices` and `clients` using `client_id` and groups by `state` and `city` to calculate total sales.
- **Clarity**: The `USING(client_id)` syntax is concise, assuming `client_id` is the common column name.
- **Potential Issue**: `NULL` values in `state` or `city` will appear as a group. If undesirable, add `WHERE state IS NOT NULL AND city IS NOT NULL`.
- **Suggestion**:
  - Explicitly use `INNER JOIN` for clarity, though `JOIN` defaults to it.
  - Add `ORDER BY state, city` for consistent output.
  - Example:
    ```sql
    SELECT 
       state,
       city,
       SUM(invoice_total) AS total_sales
    FROM invoices i
    INNER JOIN clients USING(client_id)
    WHERE state IS NOT NULL AND city IS NOT NULL
    GROUP BY state, city
    ORDER BY state, city
    ```

### Total Payments by Date and Payment Method
```sql
SELECT 
   date,
   pm.name AS payment_method,
   SUM(amount) AS total_payments
FROM payments p
JOIN payment_methods pm
     ON p.payment_method = pm.payment_method_id
GROUP BY date, payment_method
ORDER BY date
```

#### Review
- **Correctness**: The query correctly joins `payments` and `payment_methods`, grouping by `date` and `payment_method` to sum `amount`.
- **Clarity**: Aliases (`p`, `pm`) and column names are clear, with `ORDER BY date` ensuring chronological output.
- **Potential Issue**: If `date` is a `DATETIME` column, grouping by `date` uses distinct timestamps. If only the date part is needed, use `DATE(date)` or equivalent.
- **Suggestion**:
  - Use `DATE(date)` (MySQL) or equivalent for calendar date grouping if intended.
  - Example for MySQL:
    ```sql
    SELECT 
       DATE(date) AS payment_date,
       pm.name AS payment_method,
       SUM(amount) AS total_payments
    FROM payments p
    INNER JOIN payment_methods pm
         ON p.payment_method = pm.payment_method_id
    GROUP BY DATE(date), pm.name
    ORDER BY DATE(date)
    ```

## General Recommendations
- **Consistency**: Use consistent capitalization for SQL keywords (e.g., `SELECT`, `FROM`) and table/column names for readability.
- **Error Handling**: Handle `NULL` values with `COALESCE` or `WHERE ... IS NOT NULL` where appropriate.
- **Performance**: Ensure indexes on columns used in `WHERE`, `JOIN`, and `GROUP BY` clauses (e.g., `client_id`, `invoice_date`, `payment_date`) for large datasets.
- **Documentation**: Add comments to explain complex queries or business logic, especially for subqueries or `UNION` operations.





## Client Sales and Invoice Count with Filtering
```sql
USE sql_invoicing;
SELECT 
    client_id,
    SUM(invoice_total) AS total_sales,
    COUNT(*) AS number_of_invoices
FROM invoices
GROUP BY client_id
HAVING total_sales > 500 AND number_of_invoices > 5
```

### Review
- **Correctness**: The query is correct, grouping invoices by `client_id` and calculating the total sales (`SUM(invoice_total)`) and number of invoices (`COUNT(*)`). The `HAVING` clause filters groups where total sales exceed 500 and the invoice count exceeds 5.
- **Clarity**: The query is clear, with descriptive aliases (`total_sales`, `number_of_invoices`). The `HAVING` clause is appropriately used to filter aggregated results.
- **Potential Issue**: If `invoice_total` contains `NULL` values, they are ignored by `SUM`, which is typically fine but should be confirmed based on business logic. The `USE sql_invoicing` statement assumes the database exists.
- **Suggestion**:
  - Explicitly handle `NULL` values with `COALESCE` if `invoice_total` should default to 0.
  - Consider adding an `ORDER BY` clause (e.g., `ORDER BY total_sales DESC`) for consistent output.
  - Example correction:
    ```sql
    USE sql_invoicing;
    SELECT 
        client_id,
        SUM(COALESCE(invoice_total, 0)) AS total_sales,
        COUNT(*) AS number_of_invoices
    FROM invoices
    GROUP BY client_id
    HAVING total_sales > 500 AND number_of_invoices > 5
    ORDER BY total_sales DESC;
    ```

## Customer Sales in Virginia
```sql
SELECT 
    c.customer_id,
    c.first_name,
    c.last_name,
    SUM(oi.quantity * oi.unit_price) AS total_sales
FROM customers c
JOIN orders o USING (customer_id)
JOIN order_items oi USING (order_id)
WHERE state = 'VA'
GROUP BY 
    c.customer_id,
    c.first_name,
    c.last_name
```

### Review
- **Correctness**: The query is correct, joining `customers`, `orders`, and `order_items` tables to calculate total sales (`quantity * unit_price`) for customers in Virginia (`state = 'VA'`). The `GROUP BY` includes all non-aggregated columns (`customer_id`, `first_name`, `last_name`).
- **Clarity**: The use of `USING` is concise, assuming `customer_id` and `order_id` are common column names. Aliases (`c`, `o`, `oi`) enhance readability.
- **Potential Issue**: 
  - If `quantity` or `unit_price` contains `NULL` values, the product will be `NULL`, potentially underreporting sales. Use `COALESCE` to handle this.
  - Including `first_name` and `last_name` in the `GROUP BY` is unnecessary if `customer_id` is unique, as it may increase processing time.
  - The `WHERE state = 'VA'` assumes `state` is in the `customers` table; confirm this to avoid errors.
- **Suggestion**:
  - Simplify `GROUP BY` to only `customer_id` if it uniquely identifies customers.
  - Use `COALESCE` for `quantity` and `unit_price`.
  - Add `ORDER BY total_sales DESC` for better presentation.
  - Example correction:
    ```sql
    SELECT 
        c.customer_id,
        c.first_name,
        c.last_name,
        SUM(COALESCE(oi.quantity, 0) * COALESCE(oi.unit_price, 0)) AS total_sales
    FROM customers c
    JOIN orders o USING (customer_id)
    JOIN order_items oi USING (order_id)
    WHERE c.state = 'VA'
    GROUP BY c.customer_id
    ORDER BY total_sales DESC;
    ```
## WITH ROLLUP
## Sales by State and City with Rollup
```sql
SELECT 
    state,
    city,
    SUM(invoice_total) AS total_sales
FROM invoices i
JOIN clients c USING (client_id)
GROUP BY state, city WITH ROLLUP
```

### Review
- **Correctness**: The query is correct, grouping invoices by `state` and `city` and using `WITH ROLLUP` to include subtotals and a grand total. The `JOIN` with `clients` retrieves `state` and `city`.
- **Clarity**: The query is clear, with `USING(client_id)` simplifying the join syntax. The `WITH ROLLUP` clause adds summary rows for each `state` and a grand total.
- **Potential Issue**:
  - `NULL` values in `state` or `city` will appear as a group, which may be confused with `ROLLUP` summary rows (where `city` or both columns are `NULL`).
  - `WITH ROLLUP` may not be supported in all databases (e.g., older MySQL versions or some SQL Server versions); verify compatibility.
- **Suggestion**:
  - Filter out `NULL` values in `state` and `city` if they are not meaningful (e.g., `WHERE state IS NOT NULL AND city IS NOT NULL`).
  - Add `ORDER BY state, city` for consistent output, noting that `ROLLUP` summary rows use `NULL` for aggregated levels.
  - Example correction:
    ```sql
    SELECT 
        state,
        city,
        SUM(invoice_total) AS total_sales
    FROM invoices i
    JOIN clients c USING (client_id)
    WHERE c.state IS NOT NULL AND c.city IS NOT NULL
    GROUP BY state, city WITH ROLLUP
    ORDER BY state, city;
    ```

## Total Payments by Payment Method with Rollup
```sql
SELECT
    payment_method,
    SUM(amount) AS total
FROM payments p
JOIN payment_methods pm
    USING p.payment_method = pm.payment_method_id
GROUP BY payment_method WITH ROLLUP
```

### Review
- **Issue**: The syntax `USING p.payment_method = pm.payment_method_id` is incorrect. The `USING` clause requires a common column name between tables, not an equality condition. It should be `USING (payment_method)` if `payment_method` is the column name in both tables, or `ON p.payment_method = pm.payment_method_id` otherwise.
- **Correctness**: Once corrected, the query groups payments by `payment_method`, calculates the total `amount`, and uses `WITH ROLLUP` to include a grand total.
- **Clarity**: The query intent is clear, but the incorrect `USING` syntax reduces clarity. The alias `total` is concise but could be more descriptive (e.g., `total_payments`).
- **Potential Issue**:
  - If `amount` contains `NULL` values, they are ignored by `SUM`, which is typically fine but should be confirmed.
  - The `payment_method` column in the `SELECT` clause should reference `pm.name` (as in your previous query) if the `payment_methods` table stores the method name in a `name` column.
- **Suggestion**:
  - Fix the `USING` clause or replace it with `ON`.
  - Use `pm.name` as `payment_method` if that’s the column containing the payment method name.
  - Add `ORDER BY payment_method` for consistent output.
  - Example correction (assuming `payment_method` is the common column):
    ```sql
    SELECT 
        pm.name AS payment_method,
        SUM(COALESCE(p.amount, 0)) AS total_payments
    FROM payments p
    JOIN payment_methods pm USING (payment_method)
    GROUP BY pm.name WITH ROLLUP
    ORDER BY pm.name;
    ```
  - Alternative (if column names differ):
    ```sql
    SELECT 
        pm.name AS payment_method,
        SUM(COALESCE(p.amount, 0)) AS total_payments
    FROM payments p
    JOIN payment_methods pm ON p.payment_method = pm.payment_method_id
    GROUP BY pm.name WITH ROLLUP
    ORDER BY pm.name;
    ```

## General Recommendations
- **Consistency**: Use consistent capitalization for SQL keywords (e.g., `SELECT`, `FROM`) and table/column names to enhance readability.
- **Error Handling**: Use `COALESCE` to handle `NULL` values in aggregated columns (e.g., `invoice_total`, `amount`) to ensure accurate calculations.
- **Performance**: Ensure indexes exist on columns used in `JOIN`, `WHERE`, `GROUP BY`, and `HAVING` clauses (e.g., `client_id`, `customer_id`, `state`) to optimize performance on large datasets.
- **Documentation**: Add comments to clarify complex logic, especially for `WITH ROLLUP` queries, which can produce `NULL` values that may confuse users.
- **Database Compatibility**: Verify that features like `WITH ROLLUP` are supported in the target database system, as support varies (e.g., MySQL supports it, but some SQL Server versions may not).
- 

## Subqueries (Scalar)
## Subquery for Single-Value Comparison
```sql
SELECT *
FROM products
WHERE unit_price > (
    SELECT unit_price
    FROM products
    WHERE product_id = 3
);
```

### Concepts Used
- **Subquery**: A query nested within another query, used here in the `WHERE` clause to return a single `unit_price` value for comparison.
- **Scalar Subquery**: The subquery returns one column and one row, used as a value in the `>` comparison.

### Review
- **Correctness**: A scalar subquery is correctly used to compare `unit_price` against a specific product’s price. The outer query filters rows based on this comparison.
- **Clarity**: The subquery clearly isolates a single value for comparison, making the logic straightforward.
- **Potential Issues**:
  - If the subquery returns no rows (e.g., `product_id = 3` doesn’t exist), it evaluates to `NULL`, causing the outer query to return no rows (`unit_price > NULL` is false).
  - If the subquery returns multiple rows, it will cause a runtime error, as scalar subqueries must return exactly one row.
- **Suggestions**:
  - Ensure the subquery always returns a single row (e.g., using `LIMIT 1` or a unique condition).
  - Handle `NULL` results with `COALESCE` or verify the subquery’s data existence with `EXISTS`.
  - Example:
    ```sql
    SELECT product_id, product_name, unit_price
    FROM products
    WHERE unit_price > COALESCE(
        (SELECT unit_price FROM products WHERE product_id = 3),
        0
    );
    ```

## Subquery with Aggregate Function
```sql
SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);
```

### Concepts Used
- **Subquery**: A nested query in the `WHERE` clause, computing the average `salary` using the `AVG` aggregate function.
- **Scalar Subquery**: Returns a single value (the average salary) for comparison.

### Review
- **Correctness**: The subquery correctly calculates the average salary, and the outer query filters employees with salaries above this value.
- **Clarity**: The use of `AVG` in a subquery is clear for comparing against a computed threshold.
- **Potential Issues**:
  - If `salary` contains `NULL` values, `AVG` ignores them, which is typically desired but should be confirmed.
  - If the `employees` table is empty, the subquery returns `NULL`, and the outer query returns no rows.
- **Suggestions**:
  - Use `COALESCE` to handle potential `NULL` results from the subquery.
  - Consider indexing the `salary` column for performance in large datasets.
  - Example:
    ```sql
    SELECT employee_id, first_name, last_name, salary
    FROM employees
    WHERE salary > COALESCE(
        (SELECT AVG(salary) FROM employees),
        0
    );
    ```
## IN and NOT IN
## NOT IN with Subquery
```sql
USE sql_store;
SELECT *
FROM products
WHERE product_id NOT IN (
    SELECT DISTINCT product_id
    FROM order_items
);
```

### Concepts Used
- **NOT IN**: Filters rows where a column’s value is not in the list returned by a subquery.
- **Subquery**: Returns a list of `product_id` values from `order_items`.
- **DISTINCT**: Ensures unique values in the subquery result to avoid redundant checks.

### Review
- **Correctness**: The `NOT IN` operator correctly filters products not present in the `order_items` table. `DISTINCT` optimizes the subquery by removing duplicates.
- **Clarity**: The concept is clear, identifying products that have not been ordered.
- **Potential Issues**:
  - If the subquery returns `NULL` values (e.g., `product_id` in `order_items` is `NULL`), `NOT IN` evaluates to false for all rows, potentially returning incorrect results.
  - `NOT IN` can be slower than `NOT EXISTS` for large datasets due to the need to check the entire subquery result.
- **Suggestions**:
  - Prefer `NOT EXISTS` for better performance and correct handling of `NULL` values.
  - Ensure indexes on `product_id` in both tables.
  - Example:
    ```sql
    USE sql_store;
    SELECT product_id, product_name
    FROM products p
    WHERE NOT EXISTS (
        SELECT 1
        FROM order_items oi
        WHERE oi.product_id = p.product_id
    );
    ```

## NOT IN with Subquery for Clients
```sql
SELECT *
FROM clients
WHERE client_id NOT IN (
    SELECT DISTINCT client_id
    FROM invoices
);
```
## EXISTS and NOT EXISTS
### Concepts Used
- **NOT IN**: Filters clients whose `client_id` is not in the subquery’s result.
- **Subquery**: Returns a list of `client_id` values from `invoices`.
- **DISTINCT**: Ensures unique `client_id` values in the subquery.

### Review
- **Correctness**: The query correctly identifies clients with no invoices using `NOT IN`.
- **Clarity**: The logic is clear, targeting clients without associated invoices.
- **Potential Issues**:
  - As with the previous query, `NULL` values in the subquery’s `client_id` can cause `NOT IN` to return incorrect results.
  - `NOT IN` may be less efficient than `NOT EXISTS` for large datasets.
- **Suggestions**:
  - Use `NOT EXISTS` to handle `NULL` values and improve performance.
  - Ensure indexes on `client_id` in both tables.
  - Example:
    ```sql
    USE sql_invoicing;
    SELECT client_id, name
    FROM clients c
    WHERE NOT EXISTS (
        SELECT 1
        FROM invoices i
        WHERE i.client_id = c.client_id
    );
    ```

## LEFT JOIN for Non-Matching Records
```sql
SELECT *
FROM clients
LEFT JOIN invoices USING (client_id)
WHERE invoice_id IS NULL;
```

### Concepts Used
- **LEFT JOIN**: Includes all rows from the left table (`clients`) and matching rows from the right table (`invoices`), with `NULL` for non-matching rows.
- **WHERE ... IS NULL**: Filters for rows where no match exists in the right table (i.e., clients with no invoices).
- **USING**: Specifies the join condition when column names are identical.

### Review
- **Correctness**: The `LEFT JOIN` with `WHERE invoice_id IS NULL` correctly identifies clients with no invoices, as non-matching rows have `NULL` in `invoices` columns.
- **Clarity**: The `LEFT JOIN` approach is a standard and clear way to find non-matching records.
- **Potential Issues**:
  - Selecting all columns (`*`) includes `NULL` columns from `invoices`, which may be unnecessary.
  - The `USING` clause assumes identical column names (`client_id`); ensure this is true.
- **Suggestions**:
  - Select specific columns from the left table for clarity.
  - Verify that `client_id` is the correct join column in both tables.
  - Example:
    ```sql
    USE sql_invoicing;
    SELECT c.client_id, c.name
    FROM clients c
    LEFT JOIN invoices i USING (client_id)
    WHERE i.invoice_id IS NULL;
    ```

## IN with Subquery for Customers
```sql
SELECT *
FROM customers 
WHERE customer_id IN (
    SELECT o.customer_id
    FROM order_items oi
    JOIN orders o USING (order_id)
    WHERE product_id = 3
);
```

### Concepts Used
- **IN**: Filters rows where `customer_id` is in the list returned by the subquery.
- **Subquery**: Retrieves `customer_id` values from `orders` joined with `order_items` where `product_id = 3`.
- **JOIN with USING**: Combines tables based on a common `order_id` column.

### Review
- **Correctness**: The query correctly identifies customers who ordered a specific product using `IN` and a subquery with a join.
- **Clarity**: The subquery with a join clearly isolates relevant customers.
- **Potential Issues**:
  - The subquery may return duplicate `customer_id` values, slowing performance; `DISTINCT` can help.
  - Selecting `*` is vague.
- **Suggestions**:
  - Add `DISTINCT` in the subquery to avoid duplicates.
  - Specify columns explicitly.
  - Ensure indexes on `order_id` and `product_id`.
  - Example:
    ```sql
    USE sql_store;
    SELECT customer_id, first_name, last_name
    FROM customers 
    WHERE customer_id IN (
        SELECT DISTINCT o.customer_id
        FROM order_items oi
        JOIN orders o USING (order_id)
        WHERE product_id = 3
    );
    ```

## JOIN with DISTINCT for Customers
```sql
SELECT DISTINCT customer_id, first_name, last_name
FROM customers c
JOIN orders o USING (customer_id)
JOIN order_items oi USING (order_id)
WHERE oi.product_id = 3;
```

### Concepts Used
- **INNER JOIN with USING**: Combines tables based on common columns (`customer_id`, `order_id`).
- **DISTINCT**: Ensures unique rows in the result, avoiding duplicate customers.
- **WHERE**: Filters rows based on a condition (`product_id = 3`).

### Review
- **Correctness**: The query correctly uses `INNER JOIN` to find customers who ordered a specific product, with `DISTINCT` ensuring unique customer records.
- **Clarity**: The use of `DISTINCT` and explicit column selection enhances clarity.
- **Potential Issues**: No significant issues, but the database context should be specified for clarity.
- **Suggestions**:
  - Add a `USE` statement for context.
  - Consider `ORDER BY` for consistent output.
  - Ensure indexes on `customer_id`, `order_id`, and `product_id`.
  - Example:
    ```sql
    USE sql_store;
    SELECT DISTINCT c.customer_id, c.first_name, c.last_name
    FROM customers c
    JOIN orders o USING (customer_id)
    JOIN order_items oi USING (order_id)
    WHERE oi.product_id = 3
    ORDER BY c.customer_id;
    ```

## Subquery with MAX for Invoices
```sql
USE sql_invoicing;
SELECT *
FROM invoices
WHERE invoice_total > (
    SELECT MAX(invoice_total)
    FROM invoices
    WHERE client_id = 3
);
```

### Concepts Used
- **Subquery**: Retrieves the maximum `invoice_total` for a specific client.
- **Scalar Subquery**: Returns a single value for comparison with `invoice_total`.

### Review
- **Correctness**: The query correctly compares `invoice_total` against the maximum for `client_id = 3`.
- **Clarity**: The subquery with `MAX` is a clear way to establish a threshold.
- **Potential Issues**:
  - If no invoices exist for `client_id = 3`, the subquery returns `NULL`, and the outer query returns no rows.
- **Suggestions**:
  - Handle empty subquery results with `EXISTS` or `COALESCE`.
  - Specify columns instead of `*`.
  - Example:
    ```sql
    USE sql_invoicing;
    SELECT invoice_id, client_id, invoice_total
    FROM invoices
    WHERE invoice_total > COALESCE(
        (SELECT MAX(invoice_total) FROM invoices WHERE client_id = 3),
        0
    );
    ```
## ALL
## ALL with Subquery for Invoices
```sql
SELECT *
FROM invoices
WHERE invoice_total > ALL (
    SELECT invoice_total
    FROM invoices
    WHERE client_id = 3
);
```

### Concepts Used
- **ALL**: Compares `invoice_total` against all values returned by the subquery, requiring it to be greater than every value.
- **Subquery**: Returns a list of `invoice_total` values for `client_id = 3`.

### Review
- **Correctness**: The query is correct and equivalent to comparing against the maximum `invoice_total`, as `> ALL` means greater than every value in the subquery.
- **Clarity**: The `ALL` operator is less common and may be less intuitive than using `MAX`.
- **Potential Issues**:
  - If the subquery is empty (no invoices for `client_id = 3`), `> ALL` evaluates to true, returning all rows, which may be unintended.
  - Selecting `*` is vague.
- **Suggestions**:
  - Prefer `> (SELECT MAX(...))` for clarity and equivalence.
  - Handle empty subquery cases with `EXISTS`.
  - Specify columns explicitly.
  - Example:
    ```sql
    USE sql_invoicing;
    SELECT invoice_id, client_id, invoice_total
    FROM invoices
    WHERE invoice_total > (
        SELECT MAX(invoice_total)
        FROM invoices
        WHERE client_id = 3
    )
    AND EXISTS (
        SELECT 1
        FROM invoices
        WHERE client_id = 3
    );
    ```

## General Recommendations
- **Consistency**: Use consistent capitalization for SQL keywords (e.g., `SELECT`, `FROM`) and table/column names.
- **Clarity**: Avoid `SELECT *`; explicitly list columns for better readability and maintainability.
- **Performance**: Ensure indexes on columns used in `WHERE`, `JOIN`, and subqueries (e.g., `client_id`, `product_id`, `order_id`).
- **NULL Handling**: Be cautious with `NOT IN`, as `NULL` values in subqueries can lead to incorrect results; prefer `NOT EXISTS`. Use `COALESCE` for scalar subqueries that may return `NULL`.
- **Context**: Include `USE` statements to specify the database context.
- **Subquery Optimization**: Use `DISTINCT` in multi-row subqueries to reduce duplicates, and consider `EXISTS` or joins for better performance in some cases.

## ANY and SOME
## ANY with Subquery
```sql
SELECT *
FROM clients
WHERE client_id = ANY (
    SELECT client_id
    FROM invoices
    GROUP BY client_id
    HAVING COUNT(*) >= 2
);
```

### Concept: ANY
- **Definition**: The `ANY` operator compares a value to each value in a list returned by a subquery, returning true if the comparison is true for at least one value in the list.
- **Usage**: Used in the `WHERE` clause to filter rows where a column (e.g., `client_id`) matches any value from a subquery.
- **Subquery**: Returns a list of values (e.g., `client_id` values with at least two invoices, determined by `GROUP BY` and `HAVING`).
- **Correctness**: The `ANY` operator is correctly used to select rows where `client_id` matches any value from the subquery. It’s equivalent to using `IN` for equality comparisons.
- **Clarity**: The concept is clear, especially when paired with `GROUP BY` and `HAVING` to filter subquery results.
- **Potential Issues**:
  - If the subquery returns no rows, `ANY` evaluates to false, and no rows are returned.
  - If the subquery returns `NULL` values, the comparison may behave unexpectedly (e.g., `client_id = NULL` is false).
- **Best Practices**:
  - Use `IN` instead of `ANY` for equality comparisons, as it’s more readable and widely understood.
  - Ensure the subquery column (e.g., `client_id`) does not return `NULL` or handle `NULL` explicitly.
  - Example:
    ```sql
    SELECT client_id, name
    FROM clients
    WHERE client_id IN (
        SELECT client_id
        FROM invoices
        WHERE client_id IS NOT NULL
        GROUP BY client_id
        HAVING COUNT(*) >= 2
    );
    ```

## SOME with Subquery
```sql
SELECT *
FROM clients
WHERE client_id = SOME (
    SELECT client_id
    FROM invoices
    GROUP BY client_id
    HAVING COUNT(*) >= 2
);
```

### Concept: SOME
- **Definition**: The `SOME` operator is identical to `ANY`, comparing a value to each value in a subquery’s result, returning true if the comparison is true for at least one value.
- **Usage**: Used in the `WHERE` clause, typically with comparison operators (e.g., `=`), to filter rows based on subquery results.
- **Subquery**: Returns a list of values (e.g., `client_id` values with multiple invoices).
- **Correctness**: The `SOME` operator is correctly applied, functioning the same as `ANY` or `IN` for equality comparisons.
- **Clarity**: Less common than `IN`, `SOME` may reduce clarity for readers unfamiliar with it.
- **Potential Issues**:
  - Same as `ANY`: empty subquery results or `NULL` values can affect outcomes.
  - Less intuitive than `IN` for equality checks.
- **Best Practices**:
  - Prefer `IN` for equality comparisons due to its widespread use and clarity.
  - Ensure subquery results are non-`NULL` or handle `NULL` explicitly.
  - Example:
    ```sql
    SELECT client_id, name
    FROM clients
    WHERE client_id IN (
        SELECT client_id
        FROM invoices
        WHERE client_id IS NOT NULL
        GROUP BY client_id
        HAVING COUNT(*) >= 2
    );
    ```

## Correlated Subquery with Aggregate
```sql
USE sql_hr;
SELECT *
FROM employees e
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
    WHERE office_id = e.office_id
);
```
## Correlated Subqueries
### Concept: Correlated Subquery
- **Definition**: A subquery that references columns from the outer query, executed repeatedly for each row of the outer query.
- **Usage**: Used here to compare each employee’s `salary` to the average salary of their specific `office_id`.
- **Correctness**: The correlated subquery correctly calculates the average salary for the same `office_id` as the outer query’s current row.
- **Clarity**: The correlation between `e.office_id` and the subquery’s `WHERE` clause is clear, though correlated subqueries can be complex to read.
- **Potential Issues**:
  - Correlated subqueries can be slow for large datasets, as they execute for each outer row.
  - If no employees exist for an `office_id`, the subquery returns `NULL`, and the comparison may exclude rows.
- **Best Practices**:
  - Consider using a join with a derived table or `GROUP BY` for better performance in large datasets.
  - Handle potential `NULL` results with `COALESCE`.
  - Example:
    ```sql
    USE sql_hr;
    SELECT e.employee_id, e.first_name, e.last_name, e.salary
    FROM employees e
    JOIN (
        SELECT office_id, AVG(salary) AS avg_salary
        FROM employees
        GROUP BY office_id
    ) avg_salaries
    ON e.office_id = avg_salaries.office_id
    WHERE e.salary > COALESCE(avg_salaries.avg_salary, 0);
    ```

## Correlated Subquery for Invoices
```sql
SELECT *
FROM invoices i
WHERE invoice_total > (
    SELECT AVG(invoice_total)
    FROM invoices
    WHERE client_id = i.client_id
);
```

### Concept: Correlated Subquery
- **Definition**: A subquery that depends on the outer query’s row, executed for each row of the outer query.
- **Usage**: Compares each invoice’s `invoice_total` to the average `invoice_total` for the same `client_id`.
- **Correctness**: The subquery correctly computes the average per client, filtering invoices above this average.
- **Clarity**: The correlation is clear but may be less intuitive for complex queries.
- **Potential Issues**:
  - Slow performance for large tables due to repeated subquery execution.
  - If a `client_id` has no invoices, the subquery returns `NULL`, excluding the row.
- **Best Practices**:
  - Replace with a join and `GROUP BY` for better performance.
  - Handle `NULL` with `COALESCE` or verify data existence.
  - Example:
    ```sql
    SELECT i.invoice_id, i.client_id, i.invoice_total
    FROM invoices i
    JOIN (
        SELECT client_id, AVG(invoice_total) AS avg_total
        FROM invoices
        GROUP BY client_id
    ) avg_invoices
    ON i.client_id = avg_invoices.client_id
    WHERE i.invoice_total > COALESCE(avg_invoices.avg_total, 0);
    ```

## EXISTS with Correlated Subquery
```sql
SELECT *
FROM clients c
WHERE EXISTS (
    SELECT client_id
    FROM invoices
    WHERE client_id = c.client_id
);
```

### Concept: EXISTS
- **Definition**: The `EXISTS` operator checks if a subquery returns at least one row, returning true or false.
- **Correlated Subquery**: The subquery references the outer query’s `client_id` to check for related invoices.
- **Usage**: Filters clients who have at least one invoice.
- **Correctness**: The `EXISTS` clause correctly identifies clients with matching invoices.
- **Clarity**: The use of `EXISTS` is clear and efficient for checking existence.
- **Potential Issues**:
  - Selecting all columns (`*`) may include unnecessary data.
  - Performance depends on indexing of `client_id` in `invoices`.
- **Best Practices**:
  - Select specific columns for clarity.
  - Ensure indexes on join columns (e.g., `client_id`).
  - Example:
    ```sql
    SELECT c.client_id, c.name
    FROM clients c
    WHERE EXISTS (
        SELECT 1
        FROM invoices
        WHERE client_id = c.client_id
    );
    ```

## NOT EXISTS with Correlated Subquery
```sql
SELECT *
FROM products p
WHERE NOT EXISTS (
    SELECT product_id
    FROM order_items
    WHERE product_id = p.product_id
);
```

### Concept: NOT EXISTS
- **Definition**: The `NOT EXISTS` operator checks if a subquery returns no rows, returning true if no matching rows are found.
- **Correlated Subquery**: Checks for `order_items` with the same `product_id` as the outer query’s row.
- **Usage**: Filters products that have no associated order items.
- **Correctness**: The query correctly identifies products not ordered, using `NOT EXISTS` for absence checks.
- **Clarity**: The `NOT EXISTS` approach is clear and typically more efficient than `NOT IN` for handling `NULL` values.
- **Potential Issues**:
  - Selecting `*` is vague.
  - Performance depends on indexing of `product_id`.
- **Best Practices**:
  - Select specific columns.
  - Use `SELECT 1` in the subquery for efficiency, as the result content is irrelevant.
  - Example:
    ```sql
    SELECT p.product_id, p.product_name
    FROM products p
    WHERE NOT EXISTS (
        SELECT 1
        FROM order_items
        WHERE product_id = p.product_id
    );
    ```

## Subquery in SELECT Clause
```sql
SELECT
    invoice_id,
    invoice_total,
    (SELECT AVG(invoice_total) FROM invoices) AS invoice_average,
    invoice_total - (SELECT invoice_average) AS difference
FROM invoices;
```
## Subqueries in SELECT Clause
### Concepts: Subquery in SELECT
- **Definition**: Subqueries in the `SELECT` clause compute a value for each row of the outer query, included as a column.
- **Usage**: Calculates the overall average `invoice_total` and the difference between each `invoice_total` and this average.
- **Correctness**: The subquery correctly computes the average, but the second subquery (`SELECT invoice_average`) is invalid, as it references a column alias (`invoice_average`) not yet defined.
- **Clarity**: Using a subquery for the average is clear, but the invalid reference reduces clarity.
- **Potential Issues**:
  - The `difference` calculation fails due to the invalid subquery reference.
  - Repeated execution of the same subquery (`AVG`) can be inefficient.
- **Best Practices**:
  - Use a derived table or common table expression (CTE) to compute the average once.
  - Reference the alias directly in the calculation.
  - Example:
    ```sql
    WITH avg_invoice AS (
        SELECT AVG(invoice_total) AS invoice_average
        FROM invoices
    )
    SELECT
        invoice_id,
        invoice_total,
        (SELECT invoice_average FROM avg_invoice) AS invoice_average,
        invoice_total - (SELECT invoice_average FROM avg_invoice) AS difference
    FROM invoices;
    ```

## Multiple Subqueries in SELECT Clause
```sql
SELECT 
    client_id,
    name,
    (SELECT SUM(invoice_total) FROM invoices WHERE client_id = c.client_id) AS total_sales,
    (SELECT AVG(invoice_total) FROM invoices) AS average,
    (SELECT total_sales - average) AS difference
FROM clients c;
```

### Concepts: Subqueries in SELECT, Correlated Subquery
- **Definition**: Multiple subqueries in the `SELECT` clause compute values (e.g., total sales per client, overall average) for each row.
- **Correlated Subquery**: The `SUM` subquery uses the outer query’s `client_id` to calculate client-specific totals.
- **Usage**: Displays client details, their total sales, the overall invoice average, and the difference.
- **Correctness**: The `total_sales` and `average` subqueries are correct, but the `difference` subquery is invalid, as it references aliases (`total_sales`, `average`) not yet available.
- **Clarity**: The intent is clear, but the invalid `difference` subquery causes confusion.
- **Potential Issues**:
  - The `difference` subquery fails due to alias referencing.
  - Correlated subqueries (`SUM`) can be slow for large datasets.
- **Best Practices**:
  - Compute aggregates in a derived table or CTE for efficiency.
  - Calculate differences directly in the outer query.
  - Example:
    ```sql
    WITH invoice_stats AS (
        SELECT AVG(invoice_total) AS invoice_average
        FROM invoices
    )
    SELECT 
        c.client_id,
        c.name,
        (SELECT SUM(invoice_total) FROM invoices WHERE client_id = c.client_id) AS total_sales,
        (SELECT invoice_average FROM invoice_stats) AS average,
        (SELECT SUM(invoice_total) FROM invoices WHERE client_id = c.client_id) - (SELECT invoice_average FROM invoice_stats) AS difference
    FROM clients c;
    ```

## Derived Table with Subqueries
```sql
SELECT *
FROM (
    SELECT 
        client_id,
        name,
        (SELECT SUM(invoice_total) FROM invoices WHERE client_id = c.client_id) AS total_sales,
        (SELECT AVG(invoice_total) FROM invoices) AS average,
        (SELECT total_sales - average) AS difference
    FROM clients c
) AS sales_summary
WHERE total_sales IS NOT NULL;
```
## Derived Tables
### Concepts: Derived Table, Subqueries in SELECT
- **Definition**: A derived table is a subquery in the `FROM` clause, treated as a temporary table with an alias (e.g., `sales_summary`).
- **Correlated Subquery**: Computes client-specific totals.
- **Usage**: Wraps a query with subqueries to filter results (e.g., excluding clients with no sales).
- **Correctness**: The derived table is valid, but the `difference` subquery is incorrect due to invalid alias referencing. The `WHERE` clause correctly filters non-`NULL` `total_sales`.
- **Clarity**: The derived table adds structure, but the `difference` error reduces clarity.
- **Potential Issues**:
  - The `difference` subquery fails.
  - Correlated subqueries are inefficient for large datasets.
- **Best Practices**:
  - Use a CTE or join for aggregates to avoid repeated subquery execution.
  - Compute differences directly in the outer query.
  - Example:
    ```sql
    WITH invoice_stats AS (
        SELECT AVG(invoice_total) AS invoice_average
        FROM invoices
    )
    SELECT client_id, name, total_sales, average, total_sales - average AS difference
    FROM (
        SELECT 
            c.client_id,
            c.name,
            (SELECT SUM(invoice_total) FROM invoices WHERE client_id = c.client_id) AS total_sales,
            (SELECT invoice_average FROM invoice_stats) AS average
        FROM clients c
    ) AS sales_summary
    WHERE total_sales IS NOT NULL;
    ```

## General Recommendations
- **Consistency**: Use consistent capitalization for SQL keywords (e.g., `SELECT`, `FROM`) and table/column names.
- **Clarity**: Avoid `SELECT *`; specify columns explicitly. Use `IN` instead of `ANY`/`SOME` for readability.
- **Performance**: Replace correlated subqueries with joins or CTEs for large datasets. Ensure indexes on join and filter columns (e.g., `client_id`, `product_id`).
- **NULL Handling**: Handle `NULL` in subqueries with `COALESCE` or `EXISTS`. Prefer `NOT EXISTS` over `NOT IN` for `NULL`-safe logic.
- **Subquery Efficiency**: Use `SELECT 1` in `EXISTS`/`NOT EXISTS` subqueries, as the result content is irrelevant. Avoid referencing column aliases in subqueries.
- **Context**: Include `USE` statements to specify the database context.





## Overview
The provided SQL code demonstrates a variety of MySQL functions for numerical, string, and date/time operations, along with a practical query using the `sql_store` database. This review evaluates the code’s strengths, suggests improvements, and provides additional examples. The table below summarizes the functions covered, their categories, descriptions, and examples from the code.

| Function | Category | Description | Example |
|----------|----------|-------------|---------|
| `ROUND` | Numerical | Rounds a number to specified decimals or nearest integer | `SELECT ROUND(5.73)`, `SELECT ROUND(5.73,1)`, `SELECT ROUND(5.73423,2)` |
| `TRUNCATE` | Numerical | Truncates a number to specified decimals | `SELECT TRUNCATE(5.64223,2)` |
| `CEILING` | Numerical | Rounds up to next integer | `SELECT CEILING(5.2)` |
| `FLOOR` | Numerical | Rounds down to previous integer | `select floor(5.2)` |
| `ABS` | Numerical | Returns absolute value | `SELECT ABS(-5.3)` |
| `RAND` | Numerical | Generates random float (0 to 1) | `SELECT RAND()` |
| `LENGTH` | String | Returns string length | `SELECT LENGTH('SKI')` |
| `UPPER` | String | Converts string to uppercase | `SELECT UPPER('SKY')` |
| `LOWER` | String | Converts string to lowercase | `SELECT LOWER('Sky')` |
| `LTRIM` | String | Removes leading spaces | `SELECT LTRIM('   SKY')` |
| `RTRIM` | String | Removes trailing spaces | `SELECT RTRIM('SKY  ')` |
| `LEFT` | String | Extracts leftmost characters | `SELECT LEFT('KINDERGARDEN',4)` |
| `RIGHT` | String | Extracts rightmost characters | `SELECT RIGHT('KINDERGARDEN',3)` |
| `SUBSTRING` | String | Extracts substring from given position | `SELECT SUBSTRING('KINDERGARDEN',3,5)` |
| `LOCATE` | String | Finds position of substring | `SELECT LOCATE('n','kindergarden')`, `SELECT LOCATE('garten','Kindergarten')` |
| `REPLACE` | String | Replaces substring | `SELECT REPLACE('Kindergarten','garten','garden')` |
| `CONCAT` | String | Concatenates strings | `SELECT CONCAT('first_name','last_name')` |
| `NOW` | Date/Time | Returns current timestamp | `SELECT NOW()` |
| `CURDATE` | Date/Time | Returns current date | `SELECT CURDATE()` |
| `CURTIME` | Date/Time | Returns current time | `SELECT CURTIME()` |
| `YEAR` | Date/Time | Extracts year from date | `SELECT YEAR(NOW())` |
| `HOUR` | Date/Time | Extracts hour from time | `SELECT HOUR(NOW())` |
| `SECOND` | Date/Time | Extracts second from time | `SELECT SECOND(NOW())` |
| `DAYNAME` | Date/Time | Returns day name | `SELECT DAYNAME(NOW())` |
| `MONTHNAME` | Date/Time | Returns month name | `SELECT MONTHNAME(NOW())` |
| `EXTRACT` | Date/Time | Extracts part of date | `SELECT EXTRACT(YEAR FROM NOW()) AS YEAR` |
| `DATE_ADD` | Date/Time | Adds interval to date | `SELECT DATE_ADD(NOW(), INTERVAL 2 DAY)` |
| `DATE_SUB` | Date/Time | Subtracts interval from date | `SELECT DATE_SUB(NOW(), INTERVAL 1 YEAR)` |
| `DATEDIFF` | Date/Time | Returns days between dates | `SELECT DATEDIFF('2025-01-05','2019-01-01')`, `SELECT DATEDIFF('2025-01-05 7:00','2019-01-01 10:00')` |
| `TIME_TO_SEC` | Date/Time | Converts time to seconds | `SELECT TIME_TO_SEC('09:00') - TIME_TO_SEC('09:02')` |

## Numerical Functions
The code includes:
- `ROUND(5.73)`, `ROUND(5.73,1)`, `ROUND(5.73423,2)`: Outputs `6`, `5.7`, `5.73`.
- `TRUNCATE(5.64223,2)`: Outputs `5.64`.
- `CEILING(5.2)`: Outputs `6`.
- `FLOOR(5.2)`: Outputs `5`.
- `ABS(-5.3)`: Outputs `5.3`.
- `RAND()`: Outputs random float (e.g., `0.7234`).

**Strengths**:
- Covers essential numerical operations with clear examples.
- Shows `ROUND` with different precision levels.

**Improvements**:
- Add semicolons (e.g., `SELECT ROUND(5.73);`).
- Use uppercase keywords (e.g., `SELECT FLOOR(5.2)`).
- Include edge case: `SELECT ROUND(NULL)` (returns `NULL`).

## String Functions
The code includes:
- `LENGTH('SKI')`: Outputs `3`.
- `UPPER('SKY')`, `LOWER('Sky')`: Outputs `SKY`, `sky`.
- `LTRIM('   SKY')`, `RTRIM('SKY  ')`: Outputs `SKY`.
- `LEFT('KINDERGARDEN',4)`, `RIGHT('KINDERGARDEN',3)`: Outputs `KIND`, `DEN`.
- `SUBSTRING('KINDERGARDEN',3,5)`: Outputs `NDERG`.
- `LOCATE('n','kindergarden')`, `LOCATE('garten','Kindergarten')`: Outputs `3`, `7`.
- `REPLACE('Kindergarten','garten','garden')`: Outputs `Kindergarden`.
- `CONCAT('first_name','last_name')`: Outputs `first_namelast_name`.

**Strengths**:
- Comprehensive string manipulation functions.
- Clear examples, including single character and substring for `LOCATE`.

**Improvements**:
- Note `LOCATE` is case-insensitive in MySQL.
- Add `NULL` example: `SELECT CONCAT(NULL, 'test')` (returns `test`).
- Add semicolons.

## Practical String Application
The code includes:
- `USE sql_store; SELECT CONCAT(first_name,' ',last_name) AS full_name FROM customers`: Combines names (e.g., `John Doe`).

**Strengths**:
- Practical use of `CONCAT` with database table.
- Clear alias (`AS full_name`).

**Improvements**:
- Add schema comment (e.g., `-- Assumes customers table with first_name, last_name`).
- Include semicolon: `SELECT CONCAT(first_name,' ',last_name) AS full_name FROM customers;`.

## Date/Time Functions
The code includes:
- `NOW()`, `CURDATE()`, `CURTIME()`: Outputs current timestamp, date, time (e.g., `2025-06-04 22:38:00`, `2025-06-04`, `22:38:00`).
- `YEAR(NOW())`, `HOUR(NOW())`, `SECOND(NOW())`: Outputs year, hour, second (e.g., `2025`, `22`, `38`).
- `DAYNAME(NOW())`, `MONTHNAME(NOW())`: Outputs `Wednesday`, `June`.
- `EXTRACT(YEAR FROM NOW()) AS YEAR`: Outputs `2025`.
- `SELECT * FROM orders WHERE YEAR(order_date) = YEAR(NOW())`: Filters orders by current year.
- `DATE_ADD(NOW(), INTERVAL 2 DAY)`: Adds 2 days.
- `DATE_SUB(NOW(), INTERVAL 1 YEAR)`: Subtracts 1 year.
- `DATEDIFF('2025-01-05','2019-01-01')`, `DATEDIFF('2025-01-05 7:00','2019-01-01 10:00')`: Outputs `2196` (time ignored).
- `TIME_TO_SEC('09:00') - TIME_TO_SEC('09:02')`: Outputs `-120`.

**Strengths**:
- Wide range of date/time functions.
- Practical query filtering orders.
- `DATEDIFF` examples clarify date-only behavior.

**Improvements**:
- Add comments (e.g., `-- Returns seconds since midnight` for `TIME_TO_SEC`).
- Clarify `DATEDIFF` ignores time.
- Show edge case: `SELECT DATE_ADD(NULL, INTERVAL 1 DAY)` (returns `NULL`).

## Overall Assessment
**Strengths**:
- Broad function coverage, ideal for learning SQL.
- Simple examples clarify outputs.
- Practical `sql_store` query shows real-world use.

**Improvements**:
- Add semicolons for compatibility.
- Use uppercase SQL keywords consistently.
- Include comments explaining functions.
- Provide `sql_store` schema details.
- Show edge cases (e.g., `NULL`, invalid inputs).

## Additional Examples
1. **Numerical and String Combination**:
   ```sql
   SELECT CONCAT('Total: $', ROUND(123.456, 1)); -- Returns 'Total: $123.5'
   ```
2. **NULL Handling**:
   ```sql
   SELECT LENGTH(NULL); -- Returns NULL
   ```
3. **Random Number Range**:
   ```sql
   SELECT FLOOR(RAND() * 50) + 1; -- Random integer between 1 and 50
   ```
4. **Formatted Date**:
   ```sql
   SELECT CONCAT(DAYNAME(NOW()), ', ', MONTHNAME(NOW()), ' ', YEAR(NOW())); -- E.g., 'Wednesday, June 2025'
   ```
5. **Recent Orders Filter**:
   ```sql
   SELECT * FROM orders WHERE order_date >= DATE_SUB(NOW(), INTERVAL 7 DAY); -- Orders from last 7 days
   ```




## NULL Handling
**Related Queries**: 
- `SELECT order_id, IFNULL(shipper_id, 'Not assigned') AS shipper FROM orders`
- `SELECT order_id, COALESCE(shipper_id, comments, 'Not assigned') AS shipper FROM orders`
- `SELECT concat(first_name, last_name) AS customer, ifnull(phone, 'Unknown') AS phone FROM customers`

**Review**:
- **Concept**: NULL handling replaces missing values with meaningful defaults using `IFNULL` (MySQL-specific) or `COALESCE` (standard SQL) to improve output clarity.
- **Strengths**: 
  - `IFNULL(shipper_id, 'Not assigned')` and `IFNULL(phone, 'Unknown')` provide clear defaults for missing data.
  - `COALESCE(shipper_id, comments, 'Not assigned')` checks multiple columns, offering flexibility for fallback values.
- **Improvements**:
  - Use `COALESCE` over `IFNULL` for database portability (e.g., PostgreSQL, SQL Server).
  - Ensure `comments` is a relevant fallback for `shipper_id` to avoid misleading output.
  - Validate data types of fallback values for consistency.
- **Best Practice**: Prefer `COALESCE` for cross-database compatibility. Ensure fallback values align with the column’s purpose.

**Example**:
```sql
-- Display employee contact info, prioritizing mobile phone, then home phone, then 'No contact'
SELECT 
    employee_id,
    COALESCE(mobile_phone, home_phone, 'No contact') AS contact_number
FROM employees
WHERE department_id = 10;
```
*Use Case*: This query retrieves contact information for employees in department 10, ensuring a phone number is always displayed by checking `mobile_phone`, then `home_phone`, and defaulting to 'No contact' if both are NULL.

---

## String Concatenation
**Related Queries**:
- `SELECT concat(first_name, last_name) AS customer, ifnull(phone, 'Unknown') AS phone FROM customers`
- `SELECT CONCAT(first_name, ' ', last_name) AS customer, points, CASE ... END AS category FROM customers`

**Review**:
- **Concept**: Concatenation combines strings (e.g., names) for readable output using `CONCAT` or `CONCAT_WS` (with separator).
- **Strengths**:
  - The second query uses `CONCAT(first_name, ' ', last_name)` to create a properly spaced full name.
  - Aliasing as `customer` clarifies the output.
- **Improvements**:
  - The first query lacks a space in `concat(first_name, last_name)`, causing names to run together (e.g., "JohnDoe"). Use `CONCAT(first_name, ' ', last_name)` or `CONCAT_WS`.
  - Trim whitespace from inputs (e.g., `TRIM(first_name)`) to handle inconsistent data.
- **Best Practice**: Use `CONCAT_WS` to simplify spacing and handle NULL values automatically.

**Example**:
```sql
-- Create a formatted address string for customers
SELECT 
    customer_id,
    CONCAT_WS(', ', TRIM(street), city, state, postal_code) AS full_address
FROM customer_addresses
WHERE country = 'USA';
```
*Use Case*: This query combines address components into a single string (e.g., "123 Main St, Springfield, IL, 62701") for customers in the USA, skipping NULL fields and ensuring proper comma separation.

---

## Conditional Logic
**Related Queries**:
- `SELECT order_id, order_date, IF(YEAR(order_date) = YEAR(CURRENT_DATE), 'Active', 'Archived') AS category FROM orders`
- `SELECT product_id, name, COUNT(*) AS orders, IF(COUNT(*) > 1, 'Many times', 'Once') AS frequency FROM products JOIN order_items USING(product_id) GROUP BY product_id, name`
- `SELECT order_id, CASE WHEN YEAR(order_date) = YEAR(CURRENT_DATE) THEN 'Active' ... END AS category FROM orders`
- `SELECT CONCAT(first_name, ' ', last_name) AS customer, points, CASE WHEN points > 3000 THEN 'Gold' ... END AS category FROM customers`

**Review**:
- **Concept**: Conditional logic (`IF` and `CASE`) categorizes data based on conditions, enhancing report usability.
- **Strengths**:
  - `IF` queries provide simple binary categorization (e.g., 'Active'/'Archived', 'Many times'/'Once').
  - `CASE` queries handle multiple conditions, such as order year categories ('Active', 'Last Year', 'Archived', 'Future') and customer tiers ('Gold', 'Silver', 'Bronze').
  - The customer tier query uses `BETWEEN` and sorts by category (`ORDER BY category DESC`).
- **Improvements**:
  - Replace `NOW()` with `CURRENT_DATE` for portability (updated in the review).
  - Fix the typo `ferquency` to `frequency`.
  - Use consistent capitalization (e.g., 'Active' vs. 'active').
  - Add secondary sorting (e.g., `ORDER BY category DESC, points DESC`) for customer tiers.
  - Validate edge cases (e.g., negative `points`, future `order_date`).
- **Best Practice**: Use `CASE` for multi-condition logic. Ensure consistent output formatting and validate condition boundaries.

**Example**:
```sql
-- Categorize employees by years of service
SELECT 
    employee_id,
    CONCAT_WS(' ', first_name, last_name) AS employee_name,
    CASE 
        WHEN DATEDIFF(CURRENT_DATE, hire_date) / 365 > 10 THEN 'Veteran'
        WHEN DATEDIFF(CURRENT_DATE, hire_date) / 365 BETWEEN 5 AND 10 THEN 'Experienced'
        ELSE 'New'
    END AS service_category
FROM employees
ORDER BY service_category DESC, hire_date;
```
*Use Case*: This query categorizes employees based on years of service, sorting by category and hire date to prioritize long-serving employees within each category.

---

## Aggregation and Grouping
**Related Queries**:
- `SELECT product_id, name, COUNT(*) AS orders, IF(COUNT(*) > 1, 'Many times', 'Once') AS frequency FROM products JOIN order_items USING(product_id) GROUP BY product_id, name`
- `CREATE VIEW sales_by_client AS SELECT c.client_id, c.name, SUM(invoice_total) AS total_sales FROM clients c JOIN invoices i USING (client_id) GROUP BY client_id, name`
- `CREATE OR REPLACE VIEW Balance2 AS SELECT c.client_id, c.name, SUM(invoice_total - payment_total) AS balance FROM clients c JOIN invoices i USING(client_id) GROUP BY client_id, name`

**Review**:
- **Concept**: Aggregation (`COUNT`, `SUM`) summarizes data, with `GROUP BY` organizing results by categories.
- **Strengths**:
  - The product query uses `COUNT(*)` to tally orders, grouping by `product_id` and `name`.
  - The `sales_by_client` view aggregates `invoice_total` for total sales per client.
  - The `Balance2` view calculates outstanding balances using `SUM(invoice_total - payment_total)`.
- **Improvements**:
  - Fix the typo `ferquency` to `frequency`.
  - Ensure `name` is unique in `sales_by_client` and `Balance2` views, or group by `client_id` alone.
  - Add `ORDER BY` (e.g., `total_sales DESC`) if sorting is needed.
  - Index `product_id`, `client_id`, `invoice_total`, and `payment_total` for performance.
  - Validate non-NULL values for `invoice_total` and `payment_total`.
- **Best Practice**: Match `GROUP BY` columns with selected columns. Index join and group columns for performance.

**Example**:
```sql
-- Summarize total hours worked by department
SELECT 
    d.department_id,
    d.department_name,
    SUM(e.hours_worked) AS total_hours,
    COUNT(DISTINCT e.employee_id) AS employee_count
FROM departments d
JOIN employee_records e USING (department_id)
WHERE e.work_date >= '2025-01-01'
GROUP BY d.department_id, d.department_name
ORDER BY total_hours DESC;
```
*Use Case*: This query calculates total hours worked and the number of employees per department in 2025, sorting by total hours to identify high-workload departments.

---

## Views
**Related Queries**:
- `CREATE VIEW sales_by_client AS SELECT c.client_id, c.name, SUM(invoice_total) AS total_sales FROM clients c JOIN invoices i USING (client_id) GROUP BY client_id, name`
- `SELECT client_id, name, total_sales FROM sales_by_client ORDER BY total_sales DESC`
- `CREATE OR REPLACE VIEW Balance2 AS SELECT c.client_id, c.name, SUM(invoice_total - payment_total) AS balance FROM clients c JOIN invoices i USING(client_id) GROUP BY client_id, name`

**Review**:
- **Concept**: Views store query logic for reuse, simplifying complex queries and improving maintainability.
- **Strengths**:
  - `sales_by_client` simplifies total sales reporting.
  - `Balance2` uses `CREATE OR REPLACE` for safe updates, calculating client balances.
  - Querying `sales_by_client` with sorting leverages the view effectively.
- **Improvements**:
  - Replace `SELECT *` with explicit columns (`client_id`, `name`, `total_sales`) for clarity.
  - Ensure `name` is unique or group by `client_id` alone in views.
  - Add filters in `Balance2` (e.g., `WHERE invoice_total != payment_total`) for non-zero balances.
  - Document views with comments for maintainability.
- **Best Practice**: Use `CREATE OR REPLACE` for safe updates. List columns explicitly when querying views. Test dependent queries after view changes.

**Example**:
```sql
-- Create a view for overdue invoices
CREATE OR REPLACE VIEW overdue_invoices AS
SELECT 
    i.invoice_id,
    c.name AS client_name,
    i.invoice_total - i.payment_total AS outstanding_balance,
    i.due_date
FROM invoices i
JOIN clients c USING (client_id)
WHERE i.due_date < CURRENT_DATE
AND i.invoice_total > i.payment_total;

-- Query the view to find top overdue clients
SELECT 
    client_name,
    SUM(outstanding_balance) AS total_overdue
FROM overdue_invoices
GROUP BY client_name
ORDER BY total_overdue DESC;
```
*Use Case*: The view identifies overdue invoices, and the query summarizes total overdue amounts by client, helping prioritize collection efforts.

---

## General Recommendations
- **Portability**: Use standard SQL (`COALESCE`, `CURRENT_DATE`) over MySQL-specific functions (`IFNULL`, `NOW()`).
- **Performance**: Index columns in `JOIN`, `GROUP BY`, `WHERE`, or `ORDER BY` clauses.
- **Consistency**: Fix typos (e.g., `ferquency`), use consistent capitalization, and format outputs uniformly.
- **Validation**: Check for non-negative `points`, unique `name` in groups, and non-NULL aggregation inputs.
- **Documentation**: Add comments to views and complex queries for clarity.
