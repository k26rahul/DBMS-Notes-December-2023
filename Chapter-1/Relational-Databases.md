## Relational Databases:

🤔🍃⭐ Dominant database model due to their flexibility, data integrity, and efficient query capabilities.

**1.5.1 Core Concepts:**

* **Tables:** Data is organized into tables, each with rows (tuples) and columns (attributes).
* **Relationships:** Connections between tables are established through foreign keys, linking related data across tables.
* **Primary Keys:** Unique identifier for each row within a table, ensuring data integrity and efficient retrieval.
* **Data Types:** Define the allowed format and range of values for each attribute (e.g., integer, string, date).
* **Constraints:** Rules applied to data to ensure its accuracy and consistency (e.g., non-null, unique values).

**1.5.2 Advantages:**

* **Data Independence:** Separates logical data structure (schema) from physical storage details, allowing flexibility and schema changes without affecting applications.
* **Easy Query Formulation:** Users can retrieve data using SQL, a standardized and powerful language for expressing complex queries.
* **Data Integrity:** Constraints and relationships ensure data consistency and minimize redundancy, reducing errors and inconsistencies.
* **Support for Complex Queries:** Efficiently join data from multiple tables based on relationships, enabling powerful analysis and reporting.
* **Standardized Model:** SQL and the relational model are widely supported by various database management systems, promoting platform independence and portability.

**1.5.3 Considerations and Limitations:**

* **Not ideal for all data types:** May not be efficient for certain data types like spatial data or multimedia, requiring specialized database solutions.
* **Complex design: Designing efficient and normalized databases can be challenging, requiring expertise and careful planning.**
* **Performance concerns:** Large databases or complex queries can require careful optimization and tuning for optimal performance.
* **Limited scalability:** Traditional relational databases may face scalability limitations for very large datasets, prompting adoption of distributed or NoSQL solutions for extreme scalability needs.