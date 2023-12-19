## Relational Operations:

**1. Projection:**

* Selects specific columns from a table, reducing the returned data set.
* Useful for focusing on relevant information and reducing query complexity.
* Example: `SELECT name, age FROM Customers;` - retrieves only name and age from all customers.

**2. Selection:**

* Filters rows based on a condition, returning only rows that meet the criteria.
* Uses comparison operators (`<`, `>`, `=`, etc.), logical operators (`AND`, `OR`, `NOT`), and functions.
* Example: `SELECT * FROM Orders WHERE amount > 100;` - retrieves all orders with an amount exceeding $100.

**3. Join:**

* Combines data from multiple tables based on relationships established through foreign keys.
* Different types of joins exist:
    * **Inner Join:** Returns rows where the join condition is satisfied in both tables.
    * **Left Join:** Includes all rows from the left table and matching rows from the right table, even if there's no match.
    * **Right Join:** Opposite of left join, includes all rows from the right table and matching rows from the left table.
* Example: `SELECT c.name, o.product FROM Customers c INNER JOIN Orders o ON c.id = o.customer_id;` - retrieves customer names and ordered products where customer IDs match.

**4. Set Operations:**

* Operate on sets of rows obtained from different tables or queries:
    * **Union:** Combines all unique rows from two sets, eliminating duplicates.
    * **Intersection:** Returns rows present in both sets.
    * **Difference:** Returns rows in one set but not the other.
* Useful for merging data from different sources or finding specific data differences.
* Example: `SELECT * FROM Students (UNION) SELECT * FROM Teachers;` - combines all unique rows from Students and Teachers tables.

**5. Aggregation:**

* Applies functions to groups of rows, summarizing data:
    * **SUM:** Calculates the total of a numeric column.
    * **COUNT:** Counts the number of rows in a group.
    * **AVG:** Calculates the average of a numeric column.
* Useful for generating statistics and summaries from large datasets.
* Example: `SELECT country, COUNT(*) FROM Customers GROUP BY country;` - counts the number of customers from each country.