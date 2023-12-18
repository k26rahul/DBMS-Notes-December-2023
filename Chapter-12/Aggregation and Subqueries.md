## Aggregation and Subqueries

### Aggregation

#### 1. **SUM Aggregation**
- **Definition**: Calculates the sum of a specific column's values.
- **Example**:
  - **Table**: Consider a "Sales" table with the following data:

    | OrderID | Product     | Quantity | Price |
    |---------|-------------|----------|-------|
    | 1       | Laptop      | 2        | 1000  |
    | 2       | Smartphone  | 3        | 500   |
    | 3       | Tablet      | 1        | 300   |

  - **Query**: Calculating the total sales amount for all orders.

    ```sql
    SELECT SUM(Quantity * Price) AS TotalSales
    FROM Sales;
    ```

#### 2. **AVG Aggregation**
- **Definition**: Computes the average value of a specific column's data.
- **Example**:
  - **Table**: Consider a "Students" table with the following data:

    | StudentID | StudentName | Score |
    |----------|-------------|-------|
    | 1        | Alice       | 85    |
    | 2        | Bob         | 92    |
    | 3        | Carol       | 78    |

  - **Query**: Finding the average score of all students.

    ```sql
    SELECT AVG(Score) AS AverageScore
    FROM Students;
    ```

### Subqueries

#### 1. **Scalar Subquery**
- **Definition**: A subquery that returns a single value.
- **Example**:
  - **Tables**: Consider two tables, "Employees" and "Salaries."

    **Employees Table:**
    | EmployeeID | EmployeeName |
    |------------|--------------|
    | 1          | Alice        |
    | 2          | Bob          |
    | 3          | Carol        |

    **Salaries Table:**
    | EmployeeID | Salary |
    |------------|--------|
    | 1          | 50000  |
    | 2          | 60000  |

  - **Query**: Retrieving the name of the employee with the highest salary.

    ```sql
    SELECT EmployeeName
    FROM Employees
    WHERE EmployeeID = (SELECT EmployeeID FROM Salaries ORDER BY Salary DESC LIMIT 1);
    ```

#### 2. **Correlated Subquery**
- **Definition**: A subquery that depends on values from the outer query.
- **Example**:
  - **Tables**: Consider two tables, "Orders" and "Customers."

    **Orders Table:**
    | OrderID | CustomerID | TotalAmount |
    |---------|------------|-------------|
    | 1       | 101        | 500         |
    | 2       | 102        | 300         |
    | 3       | 103        | 800         |

    **Customers Table:**
    | CustomerID | CustomerName |
    |------------|--------------|
    | 101        | Alice        |
    | 102        | Bob          |
    | 103        | Carol        |

  - **Query**: Finding customers whose total order amount exceeds the average order amount.

    ```sql
    SELECT CustomerName
    FROM Customers
    WHERE EXISTS (
        SELECT 1
        FROM Orders
        WHERE Customers.CustomerID = Orders.CustomerID
        AND TotalAmount > (SELECT AVG(TotalAmount) FROM Orders)
    );
    ```
