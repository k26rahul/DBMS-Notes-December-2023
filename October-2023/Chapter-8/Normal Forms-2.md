1. **First Normal Form (1NF):**
   - The first normal form requires that each column in a table be atomic, which means that it should hold only a single value.
   - It also mandates that each entry in a column must be of the same data type.
   - Example: Consider a table for storing customer orders. This table violates 1NF because it contains a column for "Items" with multiple values separated by commas.
   
   | OrderID | Customer | Items            |
   | ------- | -------- | ---------------- |
   | 1      | Alice    | Apple, Banana    |
   | 2      | Bob      | Orange, Grape    |

   To bring it into 1NF, you could create a new table for items and link them to the orders through a foreign key.

2. **Second Normal Form (2NF):**
   - A table is in 2NF if it is in 1NF and all non-key attributes are fully functionally dependent on the entire primary key.
   - Example: Let's expand the order table from the 1NF example. 

   | OrderID | Customer | Product  | Quantity |
   | ------- | -------- | -------- | -------- |
   | 1      | Alice    | Apple    | 5        |
   | 1      | Alice    | Banana   | 3        |
   | 2      | Bob      | Orange   | 2        |
   | 2      | Bob      | Grape    | 4        |

   The primary key is (OrderID, Product). This table is not in 2NF since Quantity depends only on part of the primary key (OrderID). To bring it into 2NF, you can create a new table for OrderDetails.

3. **Third Normal Form (3NF):**
   - A table is in 3NF if it is in 2NF and has no transitive dependencies. In other words, non-key attributes should not depend on other non-key attributes.
   - Example: Continuing with the order example, consider a table like this:

   | OrderID | Customer | Country | ShippingCost |
   | ------- | -------- | ------- | ------------ |
   | 1      | Alice    | USA     | 10.00        |
   | 2      | Bob      | Canada  | 12.00        |

   Here, ShippingCost depends on the Country, which is not a primary key. This violates 3NF. To bring it into 3NF, you can create a separate Countries table with a CountryCode as the primary key.

4. **Boyce-Codd Normal Form (BCNF):**
   - BCNF is a more stringent form of normalization that ensures that for every non-trivial functional dependency, the left-hand side must be a superkey.
   - Example: Consider a simple table of students and their courses:

   | StudentID | CourseID | Instructor |
   | --------- | -------- | ---------- |
   | 1         | Math101  | Mr. Smith  |
   | 2         | Math101  | Mr. Johnson |
   | 3         | CS201    | Mrs. Davis  |

   In this case, {StudentID, CourseID} is a candidate key. However, Instructor depends on CourseID, which is not a superkey. To achieve BCNF, you need to create a separate table for courses.