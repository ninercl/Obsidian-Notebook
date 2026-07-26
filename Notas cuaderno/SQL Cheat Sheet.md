#SQL #CheatSheet #BasesDeDatos


## 1. SELECT Statements

- **Basic SELECT Statement:**
    
    ```sql
    SELECT column1, column2 FROM table_name;
    ```
    
- **SELECT All Columns:**
    
    ```sql
    SELECT * FROM table_name;
    ```
    
- **DISTINCT Values:**
    
    ```sql
    SELECT DISTINCT column1 FROM table_name;
    ```
    

## 2. Filtering Data

- **WHERE Clause:**
    
    ```sql
    SELECT * FROM table_name WHERE condition;
    ```
    
- **Comparison Operators:**
    
    ```sql
    =, <>, !=, <, >, <=, >=
    ```
    
- **Logical Operators:**
    
    ```sql
    AND, OR, NOT
    ```
    
- **BETWEEN:**
    
    ```sql
    SELECT * FROM table_name WHERE column BETWEEN value1 AND value2;
    ```
    
- **IN:**
    
    ```sql
    SELECT * FROM table_name WHERE column IN (value1, value2, value3);
    ```
    
- **LIKE (for patterns):**
    
    ```sql
    SELECT * FROM table_name WHERE column LIKE 'pattern';
    ```
    
    - `%` for any number of characters
    - `_` for a single character

## 3. Sorting Data

- **ORDER BY Clause:**
    
    ```sql
    SELECT * FROM table_name ORDER BY column ASC;
    SELECT * FROM table_name ORDER BY column DESC;
    ```
    

## 4. Aggregating Data

- **Aggregate Functions:**
    
    ```sql
    COUNT(), SUM(), AVG(), MAX(), MIN()
    ```
    
- **GROUP BY:**
    
    ```sql
    SELECT column, COUNT(*) FROM table_name GROUP BY column;
    ```
    
- **HAVING (filter aggregated data):**
    
    ```sql
    SELECT column, COUNT(*) FROM table_name GROUP BY column HAVING COUNT(*) > 10;
    ```
    

## 5. Joining Tables

- **INNER JOIN:**
    
    ```sql
    SELECT columns FROM table1
    INNER JOIN table2 ON table1.column = table2.column;
    ```
    
- **LEFT JOIN:**
    
    ```sql
    SELECT columns FROM table1
    LEFT JOIN table2 ON table1.column = table2.column;
    ```
    
- **RIGHT JOIN:**
    
    ```sql
    SELECT columns FROM table1
    RIGHT JOIN table2 ON table1.column = table2.column;
    ```
    
- **FULL OUTER JOIN:**
    
    ```sql
    SELECT columns FROM table1
    FULL OUTER JOIN table2 ON table1.column = table2.column;
    ```
    

## 6. Subqueries

- **Subquery in WHERE:**
    
    ```sql
    SELECT * FROM table_name WHERE column = (SELECT value FROM another_table);
    ```
    
- **Subquery in FROM:**
    
    ```sql
    SELECT sub.column FROM (SELECT * FROM table_name) AS sub;
    ```
    

## 7. Modifying Data

- **INSERT:**
    
    ```sql
    INSERT INTO table_name (column1, column2) VALUES (value1, value2);
    ```
    
- **UPDATE:**
    
    ```sql
    UPDATE table_name SET column1 = value1 WHERE condition;
    ```
    
- **DELETE:**
    
    ```sql
    DELETE FROM table_name WHERE condition;
    ```
    

## 8. Constraints

- **NOT NULL:** Ensures a column cannot have NULL values.
- **UNIQUE:** Ensures all values in a column are different.
- **PRIMARY KEY:** Combines NOT NULL and UNIQUE.
- **FOREIGN KEY:** Ensures referential integrity.
- **CHECK:** Ensures a condition is met.

## 9. Useful Functions

- **String Functions:**
    
    ```sql
    CONCAT(), LENGTH(), SUBSTRING(), LOWER(), UPPER()
    ```
    
- **Date Functions:**
    
    ```sql
    NOW(), CURDATE(), DATEDIFF(), DATE_ADD(), DATE_SUB()
    ```
    
- **Mathematical Functions:**
    
    ```sql
    ROUND(), ABS(), CEIL(), FLOOR()
    ```
    

## 10. Database Management

- **Create Database:**
    
    ```sql
    CREATE DATABASE database_name;
    ```
    
- **Create Table:**
    
    ```sql
    CREATE TABLE table_name (
        column1 datatype,
        column2 datatype,
        PRIMARY KEY (column1)
    );
    ```
    
- **Drop Table or Database:**
    
    ```sql
    DROP TABLE table_name;
    DROP DATABASE database_name;
    ```