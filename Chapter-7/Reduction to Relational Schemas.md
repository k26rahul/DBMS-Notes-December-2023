**Reduction to Relational Schemas** is the process of structuring and organizing data in a way that can be represented as tables (relations) in a relational database management system (RDBMS).

**Scenario**: Imagine you're tasked with creating a database to manage a library's book collection. You have a conceptual data model that includes the following entity:

- Entity: Books
  - Attributes: ISBN (International Standard Book Number), Title, Author, Genre, and Published Year.

Here's how you would reduce this conceptual model to relational schemas:

**1. Relational Schema**:
   - Create a relational schema that represents the data structure for the database. In this case, we'll create a single table to represent the `Books` entity.

**2. Mapping Entities to Tables**:
   - The `Books` entity in the conceptual model becomes a `Books` table in the relational schema. This table will store information about books.

**3. Attributes to Columns**:
   - Map each attribute from the conceptual model to columns in the `Books` table.

**4. Primary Keys**:
   - To ensure each book's uniqueness, designate the `ISBN` as the primary key for the `Books` table. This guarantees that every book record can be uniquely identified using its ISBN.

**Books Table**:
| ISBN       | Title          | Author      | Genre   | Published Year |
|------------|----------------|-------------|---------|-----------------|
| 978-0451524935 | `1984`     | George Orwell | Fiction | 1949          |
| 978-0061120084 | `To Kill a Mockingbird` | Harper Lee | Fiction | 1960 |
| ...        | ...            | ...         | ...     | ...             |

👉 In this example, the `Books` entity from the conceptual data model is reduced to a relational schema, which is represented as a table in a relational database. Each attribute maps to a column, and the `ISBN` is designated as the primary key for unique identification.

👉 This process simplifies the data model and makes it ready for database implementation, enabling efficient data storage, retrieval, and management of the library's book collection.


# December-Version


**Reduction to Relational Schemas**

- Process: Structure data for relational databases.
  
**Scenario: Library Database**

```
+---------------+        +------------------------+
|    Authors    |        |         Books          |
+---------------+        +------------------------+
| AuthorID (PK) |--------| ISBN (PK)              |
| AuthorName    |        | Title                  |
| BirthYear     |        | AuthorID (FK)          |
+---------------+        | Genre                  |
                         | Published Year         |
                         +------------------------+
```

In this diagram:

- `(PK)` denotes the primary key.
- `(FK)` denotes the foreign key (connection between Authors and Books through AuthorID).
- Lines connecting tables represent relationships between them.

Entities:

- Entity: Books
  - Attributes: ISBN, Title, Author, Genre, Published Year.

- Entity: Authors
  - Attributes: AuthorID, AuthorName, BirthYear.

**To-Do: Conversion to Relational Schema**

- Objective: Convert entities (Authors, Books) into an efficient relational schema for database implementation.

- Steps:
  1. Identify key entities and attributes.
  2. Design relational tables (Authors, Books).
  3. Define primary keys (AuthorID, ISBN) for unique identification.
  4. Establish relationships (AuthorID as foreign key in Books).
  5. Map attributes to table columns.
  
- Result: Streamlined data model, ready for effective storage, retrieval, and management in a relational database.

**1. Mapping Entities to Tables**:
   - `Books` table for book data.
   - `Authors` table for author data.

**2. Attributes to Columns**:
   - Map attributes to columns in each table.

**3. Primary Keys**:
   - `Books`: `ISBN` as primary key.
   - `Authors`: `AuthorID` as primary key.

**Books Table**:
| ISBN       | Title          | AuthorID | Genre   | Published Year |
|------------|----------------|----------|---------|-----------------|
| 978-0451524935 | `1984`     | 1        | Fiction | 1949          |
| 978-0061120084 | `To Kill a Mockingbird` | 2 | Fiction | 1960 |
| ...        | ...            | ...      | ...     | ...             |

**Authors Table**:
| AuthorID | AuthorName       | BirthYear |
|----------|------------------|-----------|
| 1        | George Orwell    | 1903      |
| 2        | Harper Lee        | 1926      |
| ...      | ...              | ...       |

👉 Entities `Books` and `Authors` result in two relational schemas — tables in a relational database. Each table has designated primary keys (`ISBN` and `AuthorID`) for unique identification.

👉 This structure facilitates efficient storage, retrieval, and management of the library's book collection, including author information.