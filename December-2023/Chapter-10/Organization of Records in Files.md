**Fixed-Length Records**:
In a library database, a fixed-length record structure is used to store book information.

- Record Length: Each record is always 100 characters long, regardless of content.
- Fields:
  - Title (30 characters)
  - Author (20 characters)
  - ISBN (13 characters)
  - Publication Year (4 characters)
  - Genre (10 characters)
  - Availability (4 characters)
  - Total Pages (4 characters)
  - Price (15 characters)
  - Condition (10 characters)
- Consistency: Fields maintain a constant length, simplifying record location.

**Variable-Length Records**:
In an e-commerce database, a variable-length record structure is used for customer orders.
- Record Length: Varies depending on the number of items ordered.
- Fields:
  - Order ID (8 characters)
  - Customer Name (variable length)
  - Shipping Address (variable length)
  - Order Date (10 characters)
  - Products (variable length, depends on the number of items)
- Flexibility: Record length adapts to the number of items in each order, resulting in shorter or longer records accordingly.