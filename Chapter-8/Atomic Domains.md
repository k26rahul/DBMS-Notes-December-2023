**Table Structure with Violation of Atomic Domains:**

Original Table "OrderDetails":

| OrderID | Product             | Quantity |
|---------|---------------------|----------|
| 1       | Laptop, Mouse       | 2        |
| 2       | Smartphone, Earbuds | 3        |
| 3       | Tablet, Keyboard    | 1        |

The "Product" column in the "OrderDetails" table violates atomic domain principles by storing multiple products in a single cell.

**Solution to Achieve Atomic Domains:**

To ensure atomic domains, we need to split the "Product" attribute into a separate "Products" table and reference it using a foreign key.

**New "Products" Table:**

| ProductID | ProductName  |
|-----------|--------------|
| 1         | Laptop       |
| 2         | Mouse        |
| 3         | Smartphone   |
| 4         | Earbuds      |
| 5         | Tablet       |
| 6         | Keyboard     |

**Revised "OrderDetails" Table:**

Updated "OrderDetails" table referencing "Products":

| OrderID | ProductID | Quantity |
|---------|-----------|----------|
| 1       | 1         | 2        |
| 1       | 2         | 2        |
| 2       | 3         | 3        |
| 2       | 4         | 3        |
| 3       | 5         | 1        |
| 3       | 6         | 1        |

This modification ensures atomic domains, improves efficiency, and maintains data integrity.