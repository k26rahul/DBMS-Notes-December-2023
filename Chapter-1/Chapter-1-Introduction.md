## Chapter 1 Introduction

**1.1 Database-System Applications:**

* **Traditional Applications:** Payroll, accounting, banking, inventory management, reservations, manufacturing, marketing, scientific data management, etc.
* **Emerging Applications:** Web-based applications, e-commerce, multimedia databases, real-time data processing, data warehousing, bioinformatics, etc.

**1.2 Purpose of Database Systems:**

* **Data Integration and Sharing:** Eliminate data redundancy and inconsistency, improve data availability and accessibility.
* **Improved Data Management:** Facilitate data manipulation (insert, update, delete), efficient querying and retrieval, enforce data integrity constraints.
* **Decision Support and Analysis:** Provide tools for data analysis, reporting, and knowledge discovery (data mining).
* **Improved Productivity and Efficiency:** Reduce application development time, simplify maintenance, enable concurrent access and transaction management.

**1.3 View of Data:**

* **Data Independence:** Separate logical view of data (schema) from physical storage details (structure).
* **Entity-Relationship Modeling:** Model real-world entities, relationships, and attributes using ER diagrams.
* **Relational Model:** Data organized in tables (relations) with rows (tuples) and columns (attributes), relationships expressed through foreign keys.

**1.4 Database Languages:**

* **Data Definition Language (DDL):** Create, modify, and drop database objects (tables, schemas, indexes).
* **Data Manipulation Language (DML):** Insert, update, delete, and retrieve data from the database.
* **Data Query Language (DQL):** Formulate queries to retrieve specific data based on conditions and requirements (e.g., SQL).
* **Database Administration Language (DDL):** Grant privileges, manage users, perform database maintenance tasks.

**1.5 Relational Databases:**

* **Dominant database model:** Based on relations (tables), widely used, standardized (SQL).
* **Advantages:** Data independence, easy query formulation, data integrity constraints, support for complex queries.
* **Disadvantages:** May not be efficient for certain data types (e.g., spatial data), complex database design needed for performance.

**1.6 Database Design:**

* ~~**Normalization:** Process of organizing data to minimize redundancy and maximize data integrity.~~
* **Entity-Relationship (ER) Modeling:** Visually represent entities, relationships, and attributes for effective database design.
* ~~**Normalization Forms (1NF, 2NF, 3NF):** Increasing levels of normalization to eliminate redundancy and ensure data integrity.~~
* **Database Tuning:** Optimize database performance by considering indexing, query optimization, and physical storage strategies.

**1.7 Data Storage and Querying:**

* **Physical Storage Structures:** Files, indexes, hash tables, B-trees, etc. for efficient data storage and retrieval.
* **Query Optimization:** Choose the most efficient execution plan for a given query to minimize processing time.
* **Indexing:** Improves query performance by creating additional access structures for frequently used columns.
* **Query Execution:** Parsing, query planning, optimization, and retrieval phases ensure efficient execution of user queries.

**1.8 Transaction Management:**

* **ACID Properties:** Atomicity, Consistency, Isolation, Durability guarantee reliable data manipulation even in concurrent environments.
* **Concurrency Control:** Mechanisms to prevent conflicts and ensure data integrity when multiple users access the database simultaneously.
* **Recovery Management:** Restore database to a consistent state after failures or errors through backups, logs, and rollback mechanisms.

**1.9 Database Architecture:**

* **Centralized Architecture:** Single server stores and manages all data.
* **Client-Server Architecture:** Dedicated server manages the database, clients access data remotely.
* **Distributed Architecture:** Data distributed across multiple servers for scalability and fault tolerance.
* **Cloud-Based Databases:** Database hosted on remote servers accessed through the internet, simplifies administration and offers scalability.

**1.10 Data Mining and Information Retrieval:**

* **Data Mining:** Extract hidden patterns and knowledge from large datasets for business intelligence, scientific discovery, etc.
* **Information Retrieval:** Search and retrieve relevant information from large textual databases (e.g., web searches).