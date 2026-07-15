#Databases

<u>**Db2**</u>


- it was released by IBM in 1983, originally for mainframes. 
- Db2 include AI-powered functionality: Machine learning algorithms, column store, data skipping. 

- Db2 Products: 
- Db2 Database
- Db2 Warehouse 

Cloud
- Db2 on Cloud 
- Db2 Warehouse on Cloud 

Db2 Big SQL
Db2 for z/OS

Cloud Pak for Data: Fully integrated data and AI platform, 
- Runs on Red Hat OpenShift
-Enables you yo connect to data - on premises, private cloud, public cloud. 

![[Pasted image 20260706094915.png]]

---
MySQL

- Object-relational database management system. 
- Reliable, scalable, and easy to use. 
- Offers a clustered version
- Developed by Swedish company MySQL Labs
- Acquired by Sun Microsystems, then Oracle Corporation
- Played a crucial role in LAMP stack -> Foundation for creating numerous popular websites.
- MySQL has duel licensing. 
	- GNU GPL for open-source usage
	- Commercial License for embedded applications
	- Emergence of various forks: MariaDB by original MySQL developers.

--- 

![[Pasted image 20260708083759.png]]![[Pasted image 20260708083844.png]]

Inno DB:

- Transactions to ensure consistency of data
- Row-level locking to improve multi-user performance
- Clustered indexes on primary keys for performance
- Foreign key constraints to maintains data integrity

MyISAM
- Good for worloads with read operations
- Example: Data warehouse or web applications
- Uses table-level locking

NDB engine:

NDB engine:
- Supports multiple instances of MySQL servers
- Useful for applications requiring high availability, redundancy. 

![[Pasted image 20260708084328.png]]

Clustering: Connecting multiple computing resources as a unified system
Options: 
- InnoDB Storage Engine with group replication.
- MySQL Cluster Edition with NDB Storage Engine. 

![[Pasted image 20260708084539.png]]

MySQL cluster edition 

![[Pasted image 20260708084736.png]]

----
<u>**PostgreSQL**</u>

Originates from POSTGRES project:
- Research and production applications
- Across finance, aviation, and medicine. 

Postgres95: Open source, included SQL language interpreter-
- PostgreSQL -> LAPP stack 
- Extensions such as PostGIS 

![[Pasted image 20260708085410.png]]

High availability: Two node syncrhonous replication