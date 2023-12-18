**Chapter 7: Database Design and the E-R Model**

**7.1 Overview of the Design Process**
- Database Design Process:
  - Systematic approach to constructing a well-structured database.
  - Similar to building a house: plans, blueprint (design), construct.

**7.2 The Entity-Relationship Model**
- Entity:
  - Represents a real-world object or concept (e.g., "Customer," "Product").
- Relationship:
  - Describes associations between entities (e.g., "Customer buys Product").
- Attributes:
  - Characteristics or properties of entities (e.g., "Customer Name").
- Cardinality:
  - Specifies how entities can be related (e.g., "1:1," "1:N").

**7.3 Constraints**
- Entity Integrity Constraint:
  - Ensures every entity has a unique identifier (Primary Key).
  - Example: Each student having a unique student ID.
- Referential Integrity Constraint:
  - Enforces relationships and foreign keys.
  - Example: Ensuring each enrolled course is in the official course list.
- Domain Constraints:
  - Define allowable values for attributes (e.g., date format, valid product codes).
  - Example: Date format constraint (MM/DD/YYYY).

**7.4 Removing Redundant Attributes in Entity Sets**
- Normalization:
  - Process of minimizing redundancy and dependency.
  - Example: Storing customer information such as name and address in separate tables to avoid duplicating data for multiple orders.
- Functional Dependency:
  - Attribute's value determines another.
  - Example: SSN determining Employee Name (SSN -> Name).
- Anomalies:
  - Inconsistencies in data eliminated through normalization.
  - Example: Preventing different addresses for the same student in various records by storing address information separately and using normalization.

**7.5 Entity-Relationship Diagrams**
- ERD:
  - Graphical representation of the data model.
- Entity Sets:
  - Collections of similar entities.
  - Example: Set of "Customers" or "Products" on a shopping list.
- Weak Entity Sets:
  - Depend on strong entities for identification.
  - Example: "Room" in a "Building" - the room makes sense within the context of the building.
- Aggregation:
  - Combining entities into higher-level structures.
  - Example: "Department" aggregates "Employee."

**7.6 Reduction to Relational Schemas**
- Relational Schema:
  - Structure used to represent data in tables.
- Mapping Entities to Tables:
  - Converting entity types to relations.
  - Example: "Students" become one table in the relational schema.
- Attributes to Columns:
  - Mapping entity attributes to table columns.
  - Example: "Student Name" becomes a column in the "Students" table.
- Primary Keys:
  - Defining unique identifiers in tables.
  - Example: "Student ID" uniquely identifies each student in the "Students" table.

**7.7 Entity-Relationship Design Issues**
- Generalization and Specialization:
  - Representing hierarchies in ERD.
  - Example: "Employee" and "Manager" inheriting from "Person."
- Inheritance:
  - Extending attributes from superclass to subclasses.
  - Example: "Employee" inherits attributes from "Person" like "Name" and "DOB."
- Aggregation vs. Association:
  - Differentiating between whole-part structures and associations.
  - Example: Aggregation is like "Car has Wheels," while Association is just "Customer buys Product."

**7.10 Other Aspects of Database Design**
- Data Validation:
  - Ensuring data integrity through constraints.
  - Example: Allowing only valid email addresses (e.g., "user@example.com").
- Schema Refinement:
  - Improving the database schema: Reducing redundancy, ensuring data integrity, and enhancing efficiency.
  - **Example**:
    Original Schema:
    `Employee (Emp_ID, Emp_Name, Emp_Address, Emp_Department)`
    Refined Schema:
    `Employee (Emp_ID, Emp_Name, Emp_Address)`
    `Department (Dept_ID, Dept_Name)`
    `Employee_Department (Emp_ID, Dept_ID)`
- Security and Authorization:
  - Managing user access to data.
  - Example: Locking different rooms in a house - some can access the kitchen, others can't.
- Performance Optimization:
  - Enhancing database query and update performance.
  - Example: Indexing is like the table of contents in a book - helps find information faster.
    - Indexing acts as a fast reference guide, speeding up data retrieval.

**Questions**
1. Purpose of ERD?
   - Model database structure with entities, relationships, and attributes.
2. Functional dependency?
   - One attribute's value determines another.
3. Entity Integrity Constraint?
   - Ensures each entity has a unique identifier.
4. Referential Integrity Constraint?
   - Enforces data consistency by maintaining relationships.
5. How does normalization reduce redundancy?
   - Organizes data, splits tables, and removes dependencies.
6. ERD's diamond shape?
   - Represents a relationship between entities.
7. Example of 1:N relationship?
   - A customer placing multiple orders (1 customer to N orders).
8. Relational Schema?
   - Defines table structure, column names, and data types.
9. Aggregation in ERD?
   - A relationship where an entity is composed of smaller entities.
10. Entity Set?
    - Collection of similar entities.
11. Weak vs. Strong Entity Sets?
    - Weak depends on a strong entity for identification, strong sets have unique identifiers.
12. Schema Refinement's role?
    - Improves database structure, minimizes data anomalies.
13. Use of Check Constraints?
    - Define conditions for attribute values.
14. "Generalization and Specialization" in ERD?
    - Subclasses inherit attributes from a superclass.
15. Primary Key in a relational database?
    - Uniquely identifies rows in a table.
16. Indexing's impact on database performance?
    - Improves data retrieval speed.
17. "Data Validation" in database design?
    - Ensures data integrity with constraints and validation rules.
18. "Security and Authorization" purpose?
    - Controls user data access, authorizing specific actions.
19. "Cardinality" in ERD?
    - Specifies how entities relate.
20. "Normalization" improves database how?
    - Reduces redundancy and anomalies by organizing data.