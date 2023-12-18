## Join Operation

### Join Types

#### 1. **INNER JOIN**
- **Definition**: Retrieves rows from both tables where there is a match based on the specified condition.
- **Example**:
  - **Tables**: Consider two tables, "Orders" and "Customers."
  
    **Orders Table:**
    | OrderID | CustomerID | Product    |
    |---------|------------|------------|
    | 1       | 101        | Laptop     |
    | 2       | 102        | Smartphone |
    | 3       | 103        | Tablet     |

    **Customers Table:**
    | CustomerID | CustomerName | Email              |
    |------------|--------------|--------------------|
    | 101        | John Smith   | john@example.com   |
    | 102        | Jane Doe     | jane@example.com   |
    | 104        | Bob Johnson  | bob@example.com    |

  - **Query**: Retrieving orders along with customer information for matching CustomerID.

    ```sql
    SELECT Orders.OrderID, Customers.CustomerName
    FROM Orders
    INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
    ```

#### 2. **LEFT JOIN (or LEFT OUTER JOIN)**
- **Definition**: Retrieves all rows from the left table and the matching rows from the right table. Non-matching rows on the left return NULL values for the right table.
- **Example**:
  - **Tables**: Consider two tables, "Employees" and "Departments."
  
    **Employees Table:**
    | EmployeeID | EmployeeName | DepartmentID |
    |------------|--------------|--------------|
    | 1          | Alice        | 101          |
    | 2          | Bob          | 102          |
    | 3          | Carol        | 103          |

    **Departments Table:**
    | DepartmentID | DepartmentName |
    |--------------|----------------|
    | 101          | HR             |
    | 102          | Finance        |

  - **Query**: Retrieving a list of all employees and their respective departments, including those without a department.

    ```sql
    SELECT Employees.EmployeeName, Departments.DepartmentName
    FROM Employees
    LEFT JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
    ```

#### 3. **RIGHT JOIN (or RIGHT OUTER JOIN)**
- **Definition**: Retrieves all rows from the right table and the matching rows from the left table. Non-matching rows on the right return NULL values for the left table.
- **Example**:
  - **Tables**: Consider two tables, "Students" and "Courses."
  
    **Students Table:**
    | StudentID | StudentName | CourseID |
    |-----------|-------------|----------|
    | 1         | Alice       | 101      |
    | 2         | Bob         | 102      |
    | 3         | Carol       | 103      |

    **Courses Table:**
    | CourseID | CourseName  |
    |----------|-------------|
    | 101      | Math        |
    | 102      | Science     |
    | 104      | History     |

  - **Query**: Retrieving a list of all courses and students who have enrolled, including courses without students.

    ```sql
    SELECT Students.StudentName, Courses.CourseName
    FROM Students
    RIGHT JOIN Courses ON Students.CourseID = Courses.CourseID;
    ```

#### 4. **FULL JOIN (or FULL OUTER JOIN)**
- **Definition**: Retrieves all rows when there is a match in either the left or the right table. Returns NULL values when there are no matches.
- **Example**:
  - **Tables**: Consider two tables, "Suppliers" and "Products."
  
    **Suppliers Table:**
    | SupplierID | SupplierName | ProductID |
    |------------|--------------|-----------|
    | 1          | Supplier A   | 101       |
    | 2          | Supplier B   | 102       |
    | 3          | Supplier C   | 103       |

    **Products Table:**
    | ProductID | ProductName |
    |-----------|-------------|
    | 101       | Laptop      |
    | 102       | Smartphone  |
    | 104       | Tablet      |

  - **Query**: Retrieving a list of all products and their respective suppliers, including products with no supplier and suppliers with no products.

    ```sql
    SELECT Suppliers.SupplierName, Products.ProductName
    FROM Suppliers
    FULL JOIN Products ON Suppliers.ProductID = Products.ProductID;
    ```

### Notes
- **Equi-Join vs. Non-Equi Join**: Equi-Join compares two tables based on equality (=), while non-equi join uses other operators like (<, >, <=, >=) for comparisons.
- **Self-Join**: Joining a table to itself to retrieve related information, e.g., finding employees and their managers in the same "Employees" table.