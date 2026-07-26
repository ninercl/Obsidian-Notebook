#SQL #DDL #RDBMS
[[MOC - IBM Data Engineering]]

Types of Statements 

DDL (Data Definition Language): Define, change, or drop data.
DML (Data Manipulation Data): Also know as CRUD (Create, Read, Update & Delete rows)

---
Creating Tables 

- Consider schemas 
- Collect all necessaru details 
- use ERD reference

Methods for creating tables:
- Visual interface or UI tools
- SQL statements
- Using APIs

CREATE TABLE  STATEMENT

CREATE TABLE author (
AUTHOR_ID CHAR(2) PRIMARY KEY NOT NULL,
Lastname VARCHAR (15) NOT NULL,
Firstname VARCHAR(15) NOT NULL,
Email VARCHAR(15),
City VARCHAR(15)
Country CHAR (2)
)

ALter, Drop, and Truncate

ALter table to add or remove colums, modify the data type of columns, add or remove keys or constraints.

Truncate table
- Delete all the rows in a table *IMMEDIATE* means cannot be reverted
