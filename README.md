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

## 🗂 Daily Logs
### **Day 1: Install and config MySql**  
📝 **Notes**:  
> "Learning instalation of MYSQL."  


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

