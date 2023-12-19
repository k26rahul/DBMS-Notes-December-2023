- Cardinality in Relational Schema
  - Describes relationships in DB
  - 1:1, 1:N, N:M
  - 1 entity related to how many
  - Key for data integrity
  - Example: 1 student -> N courses
  - Defines table connections

## What are mapping cardinalities and why are they used? Discuss their types in brief with suitable diagrams.

- Mapping cardinalities refer to the relationship between entities in a database model, specifying how instances of one entity relate to instances of another entity.
- These cardinalities help define the nature and constraints of relationships in a database.

- Types of Mapping Cardinalities:
   - One-to-One (1:1)
   - One-to-Many (1:N)
   - Many-to-Many (N:M)

### One-to-One (1:1) Mapping Cardinality:

**Example: Author and Book**

```
+---------+            +--------+
|  Author | ---1:1---  |  Book  |
+---------+            +--------+
```

👉 Each author is associated with exactly one book (1:1), and each book is authored by only one author.

### One-to-Many (1:N) Mapping Cardinality:

**Example: Department and Employees**

```
+-------------+ ---1:N---- +-------------+
| Department  |            |  Employee   |
+-------------+            +-------------+
```

👉 Each department can have multiple employees (1:N), but each employee is associated with only one department.

### Many-to-Many (N:N) Mapping Cardinality:

**Example: Student and Course**

```
+-----------+ ---N:N--- +-----------+
|  Student  |           |  Course   |
+-----------+           +-----------+
```

👉 Multiple students can enroll in multiple courses (N:M), and vice versa.