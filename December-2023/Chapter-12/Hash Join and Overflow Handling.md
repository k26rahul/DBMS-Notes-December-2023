## Hash Join and Overflow Handling

👉 Hash joins efficiently combine data, while overflow handling ensures the join can process large datasets without running out of memory.

### Hash Join

- **Definition**: Hash join is a type of join operation used in database systems to combine data from two tables efficiently. It uses hash functions to partition and match rows from both tables.

#### Example:

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

- **Hash Join Query**: Merging the "Employees" and "Departments" tables based on the common "DepartmentID" using a hash join.

  ```sql
  SELECT Employees.EmployeeName, Departments.DepartmentName
  FROM Employees
  INNER HASH JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
  ```

- **Hash Function**: The hash join uses a hash function to partition rows from both tables based on their "DepartmentID." This ensures that rows with the same "DepartmentID" end up in the same hash bucket.

- **Merging**: The hash join combines rows from the partitions that have the same hash value, resulting in a combined result set.

### Overflow Handling

- **Definition**: Overflow handling is a crucial aspect of hash joins. When the hash buckets have too many rows to fit into memory, overflow handling is used to store the extra rows in secondary storage, typically on disk.

#### Example:

- **Tables**: Consider two large tables, "Sales" and "Products," to illustrate the need for overflow handling.

  **Sales Table:**
  | OrderID | Product     | Quantity | Price |
  |---------|-------------|----------|-------|
  | 1       | Laptop      | 2        | 1000  |
  | 2       | Smartphone  | 3        | 500   |
  | 3       | Tablet      | 1        | 300   |
  | ...     | ...         | ...      | ...   |

  **Products Table:**
  | ProductID | ProductName |
  |-----------|-------------|
  | 1         | Laptop      |
  | 2         | Smartphone  |
  | 3         | Tablet      |
  | ...       | ...         |

- **Overflow Handling**: In a hash join involving large tables, if the number of rows in a hash bucket exceeds the available memory, overflow handling comes into play. The system stores the overflowing rows in secondary storage, like a temporary disk file.

- **Efficiency**: Overflow handling ensures that hash joins can efficiently handle large datasets, as it prevents memory constraints from limiting the join process.

