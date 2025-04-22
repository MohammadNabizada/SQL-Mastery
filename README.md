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


