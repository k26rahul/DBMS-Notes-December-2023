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