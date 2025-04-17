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
| **Tools Used**   | PostgreSQL, MySQL Workbench, Jupyter|
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
