## Entity-Relationship Model

- **Definition**: The ER Model visually represents a database's structure, crucial for efficient data management.

- **Key concepts**: Entities (real-world objects), Attributes (entity characteristics), Relationships (entity associations), Cardinality (relationship occurrences), Primary Keys (entity uniqueness), Foreign Keys (inter-table links).

- **ER Diagram**:
  - **Components**: Rectangles for entities, ellipses for attributes, diamonds for relationships.
  - **Connectivity**: Lines show entity relationships, noting cardinality with "1" or "M."
  
- **Purpose**: ER Model aids:
  - Visualizing and designing database structure.
  - Defining data organization and relationships.
  - Creating a database implementation blueprint.

- **Example**: Library database ER diagram:
  - **Entities**: "Book," "Author," "Borrower."
  - **Attributes**: "Book Title," "Author Name," "Borrower Name."
  - **Relationships**: "Written by," "Borrowed by."
  - **Cardinality**: "One-to-Many" (book authors).
  - **Keys**: "Book ISBN" uniquely identifies books.