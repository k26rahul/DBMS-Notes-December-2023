## Chapter 2: Introduction to the Relational Model

**2.1 Structure of Relational Databases:**

🤔🍃⭐ The core of the relational model revolves around tables, the fundamental building blocks of a database.

Here's a breakdown:

* **Table:** A collection of related data organized into rows (tuples) and columns (attributes).
* **Row:** Represents a single instance of an entity (e.g., a customer record).
* **Column:** Represents a specific characteristic of an entity (e.g., customer name, address).
* **Attribute Domain:** Defines the valid data types and values allowed for each column.

**2.2 Database Schema:**

The schema serves as the blueprint for the database, defining its structure and rules. It encompasses:

* **Table Names:** Unique identifiers for each table within the database.
* **Attribute Names:** Unique identifiers for each column within a table.
* **Data Types:** Specifying the allowed data formats for each attribute (e.g., integer, string, date).
* **Constraints:** Rules imposed on data to ensure its accuracy and consistency (e.g., primary key, foreign key, non-null constraints).
* **Relationships:** Defined through foreign keys linking related tables (e.g., a "customer_id" in the Orders table referencing the "id" in the Customers table).

**2.3 Keys:**

Keys play a crucial role in data integrity and efficient retrieval:

* **Primary Key:** Uniquely identifies each row within a table, ensuring no duplicates and efficient access.
* **Candidate Key:** Any set of attributes that can uniquely identify a row. Multiple candidate keys might exist in a table.
* **Foreign Key:** References the primary key of another table, establishing relationships between tables and enforcing data consistency.

**2.4 Schema Diagrams:**

Visual representations of the database schema using tools like Entity-Relationship (ER) diagrams. These diagrams highlight:

* Entities (real-world objects) represented as rectangles.
* Attributes listed within their respective entity rectangles.
* Relationships between entities shown by lines and arrows.

**2.5 Relational Query Languages:**

Structured languages used to interact with relational databases:

* **Structured Query Language (SQL):** Most popular and widely-used language for querying, managing, and manipulating data.
* **Operators:** Perform specific actions on data (e.g., comparisons, arithmetic calculations, logical expressions).
* **Clauses:** Combine keywords, operators, and expressions to form complete queries (e.g., SELECT, FROM, WHERE).

**2.6 Relational Operations:**

Fundamental building blocks for constructing queries to retrieve and manipulate data:

* **Projection:** Selecting specific columns from a table.
* **Selection:** Filtering rows based on a condition.
* **Join:** Combining data from multiple tables based on relationships.
* **Set Operations:** Union, intersection, and difference between sets of rows.
* **Aggregation:** Applying functions to groups of rows (e.g., SUM, COUNT, AVG).