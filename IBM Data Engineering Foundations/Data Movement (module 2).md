The need to ove data in adn out

Reasons:
- Initially populate the entire database
- create a copy for development and testing 
- create a snapshot for disaster recovery
- Create a new table from an external source/file

Three categories:

- Back up and restore: Back up creates a file for the entire database. Restore duplicates the database precisely.
Goo for disaaster recovery and creating copies of the database 

- Import and export: Import inserts data into table from file. Export saves table data into a file. 
Import Operations: GUI, COmmand Line, Management APIs
- Load: Alternative to the import utility 
- Doesn't perform as many checks

---
Inserting Data

- Insert is not optimal for massive load of data

DB2: Source -> Target -> Define -> Finalize 