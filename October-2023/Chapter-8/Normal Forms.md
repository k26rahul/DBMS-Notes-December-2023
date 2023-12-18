## Normal Forms in Databases

Normal forms are a set of guidelines and rules used to design and structure relational databases for data organization, accuracy, and to reduce data redundancy. They ensure that data is stored efficiently, relationships are well-defined, and updates and inserts into the database are reliable.

### 1NF (First Normal Form)

1. **Definition**:
   - In 1NF, a table is said to be in the first normal form if it meets the following criteria:
     - It has a primary key that uniquely identifies each record.
     - All attributes (columns) contain only atomic (indivisible) values.
     - There are no repeating groups, and each field contains a single value.

2. **Example**:
   - Consider a table "Orders" with the following structure:
   
   **Orders Table**:
   | OrderID | ProductName            | Quantity |
   |---------|------------------------|----------|
   | 1       | Apples, Oranges, Pears | 5, 3, 2  |
   
   - This table is not in 1NF because the "ProductName" and "Quantity" columns contain multiple values.

### 2NF (Second Normal Form)

1. **Definition**:
   - A table is in 2NF if it is in 1NF and:
     - All non-key attributes are functionally dependent on the entire primary key.

2. **Example**:
   - Suppose we have the following table, "OrderDetails," with a composite primary key (OrderID and ProductID):

   **OrderDetails Table**:
   | OrderID | ProductID | Quantity |
   |---------|-----------|----------|
   | 1       | 101       | 5        |
   | 1       | 102       | 3        |
   | 2       | 101       | 2        |

   - This table is not in 2NF because the "Quantity" attribute depends on the partial key "OrderID," not the entire primary key.

### 3NF (Third Normal Form)

1. **Definition**:
   - A table is in 3NF if it is in 2NF and:
     - There are no transitive dependencies, meaning non-key attributes depend only on the primary key.

2. **Example**:
   - Consider the "Employees" table with attributes "EmployeeID," "EmployeeName," "Department," and "Location."

   **Employees Table**:
   | EmployeeID | EmployeeName | Department | Location  |
   |------------|--------------|------------|-----------|
   | 1          | Alice        | HR         | New York  |
   | 2          | Bob          | Finance    | Boston    |
   | 3          | Carol        | HR         | New York  |

   - In this table, "Location" depends on "Department" (transitive dependency) and is not directly related to the primary key "EmployeeID." To achieve 3NF, you'd need to split this table into two: "Employees" and "Departments."

### BCNF (Boyce-Codd Normal Form)

1. **Definition**:
   - A table is in BCNF if, for every non-trivial functional dependency (X -> Y), X is a superkey.

2. **Example**:
   - Let's consider a table "Students" with attributes "StudentID" and "Course" and a functional dependency "StudentID -> Course." If "StudentID" is a superkey (unique identifier), the table is in BCNF.