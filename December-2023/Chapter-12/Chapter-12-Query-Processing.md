## Chapter 12: Query Processing

### 12.1 Overview
- **Query Processing**: The process of executing user queries in a Database Management System (DBMS).
  - **Importance**: Efficient query processing ensures quick and accurate results.
  
### 12.2 Measures of Query Cost
- **Query Cost Metrics**: Methods to estimate and compare the cost of executing different queries.
  - **Factors**: Consider factors like execution time, CPU usage, and I/O operations.
  - **Example**: Calculating query cost based on the number of disk accesses required for data retrieval.

### 12.3 Selection Operation
- **Selection in DBMS**: Retrieving rows from a table based on specified conditions (WHERE clause).
  - **Example**: Retrieving all customers who made a purchase in the last month (SELECT * FROM Customers WHERE PurchaseDate > '2023-09-01').

### 12.4 Join Operation
- **Join in DBMS**: Combining data from multiple tables based on a related column.
  - **Types of Joins**: INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN.
  - **Example**: Merging the "Orders" table with the "Customers" table to find which customers placed orders (SELECT * FROM Customers INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID).

### 12.5 Other Operations
- **Aggregation**: Performing calculations on grouped data, such as SUM, AVG, COUNT.
  - **Example**: Calculating the total sales amount for each product category (SELECT Category, SUM(SalesAmount) FROM Products GROUP BY Category).
- **Subqueries**: Nesting one query within another to retrieve related data.
  - **Example**: Finding employees with the highest salary (SELECT EmployeeName FROM Employees WHERE Salary = (SELECT MAX(Salary) FROM Employees)).

### 12.6 Evaluation of Expressions
- **Expression Evaluation**: Processing mathematical or logical expressions in queries.
  - **Arithmetic Operations**: Performing calculations within queries (e.g., SELECT (Price * Quantity) AS TotalPrice).
  - **Boolean Expressions**: Using logical operators (AND, OR) to filter data based on conditions.

### 12.7 Hash Join and Overflow Handling
- **Hash Join**: A join operation using hash functions to match and combine rows from different tables efficiently.
  - **Example**: Hash joining two large tables based on a common column to join millions of rows quickly.
- **Overflow Handling**: Managing hash collisions and data that exceeds available memory.
  - **Example**: Storing overflowed data in secondary storage for retrieval when needed.

### 12.8 Summary
- **Importance of Optimization**: Emphasizing the importance of optimizing query processing for enhanced database performance.
