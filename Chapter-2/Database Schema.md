 ## Database Schema

🤔🍃⭐ The schema acts as the architect's plan for a database, defining its structure, rules, and relationships.

**Key Components of a Database Schema:**

1. **Table Names:**
   - Unique identifiers for each table, acting as containers for related data.
   - Example: `Customers`, `Orders`, `Products`

2. **Attribute Names:**
   - Unique identifiers for each column within a table, representing specific characteristics of entities.
   - Example: In the `Customers` table: `customer_id`, `name`, `email`, `address`

3. **Data Types:**
   - Specify the allowed data formats for each attribute, ensuring data integrity and efficient storage.
   - Common data types:
      - Integers (int): Whole numbers (e.g., customer_id)
      - Strings (varchar): Textual data (e.g., name, address)
      - Dates (date): Calendar dates (e.g., order_date)
      - Decimals (decimal): Floating-point numbers (e.g., price)

4. **Constraints:**
   - Rules that enforce data consistency and prevent errors:
      - **Primary Key:** Uniquely identifies each row within a table (e.g., `customer_id` in `Customers` table).
      - **Foreign Key:** References a primary key in another table, establishing relationships (e.g., `customer_id` in `Orders` table referencing `Customers`).
      - **Not Null:** Ensures a column always has a value.
      - **Unique:** Prevents duplicate values in a column.
      - **Check:** Validates data based on specific conditions.

5. **Relationships:**
   - Connections between tables, commonly defined through foreign keys:
      - **One-to-One:** Each row in one table is related to at most one row in another table.
      - **One-to-Many:** One row in one table can be related to many rows in another table.
      - **Many-to-Many:** Multiple rows in one table can be related to multiple rows in another table (often requiring a junction table).

**Example Database Schema:**

| Table Name | Attribute Name | Data Type | Constraints |
|---|---|---|---|
| Customers | customer_id | int | Primary Key |
| Customers | name | varchar(50) | Not Null |
| Customers | email | varchar(100) | Unique |
| Customers | address | varchar(255) |  |
| Orders | order_id | int | Primary Key |
| Orders | customer_id | int | Foreign Key (References Customers.customer_id) |
| Orders | order_date | date | Not Null |
| Products | product_id | int | Primary Key |
| Products | product_name | varchar(100) | Not Null |
| Products | price | decimal(10,2) |  |

**Key Points:**

- The schema serves as a fundamental guide for understanding and interacting with a database.
- It ensures data integrity, consistency, and efficient retrieval.
- Careful schema design is essential for database performance and maintainability.
- Visual tools like Entity-Relationship (ER) diagrams can aid in schema visualization and design.