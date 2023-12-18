## Chapter 8: Relational Database Design

### 8.1 Features of Good Relational Designs
- **Purpose**: The primary goal of relational database design is to create database structures that efficiently store and manage data. Effective designs exhibit the following key features:
  - **Minimal Data Redundancy**: Reducing repetition of data to conserve storage space and maintain data consistency.
  - **Data Integrity**: Ensuring the accuracy and consistency of data, preventing errors or inconsistencies.
  - **Efficient Data Retrieval and Updates**: Structuring data in a way that allows for speedy access and modification.

### 8.2 Atomic Domains and First Normal Form
- **Atomic Domains**: In the context of relational databases, it is essential that each attribute holds only indivisible, atomic values. Attributes should not contain arrays, lists, or complex data structures.
  - **Example**: In a "Person" table, the "Phone Numbers" attribute should store individual phone numbers, not lists of phone numbers for the same person.
- **First Normal Form (1NF)**: This form requires that each attribute in a relation (table) contains only atomic, indivisible values, thereby avoiding nested structures or multi-valued attributes.
  - **Example**: To achieve 1NF, a "Phone Numbers" attribute should contain a single, atomic phone number for each person in the "Person" table.

### 8.3 Decomposition Using Functional Dependencies
- **Decomposition**: In the process of relational database design, decomposition involves breaking down large tables into smaller, more manageable tables.
- **Functional Dependencies**: Functional dependencies describe the relationships between attributes within a relation. These dependencies define how certain attributes determine others based on the data.
  - **Example**: In a "Students" table, a functional dependency might be "StudentID" determines "StudentName."
- **Candidate Keys**: Candidate keys are minimal sets of attributes that can uniquely identify a tuple (row) in a relation.
  - **Example**: In a "Courses" table, "CourseCode" can be a candidate key since it can uniquely identify courses.
- **Superkeys**: Superkeys are sets of attributes that can determine all other attributes in the relation.
  - **Example**: In an "Employees" table, "EmployeeID" is a superkey because it can determine all other employee details.
- 👉 All super keys can't be candidate keys. But all candidate keys are super keys. 

### 8.4 Functional-Dependency Theory
- **Functional Dependencies**: Functional dependencies are expressed as X -> Y, indicating that if you know the values of X, you can determine the values of Y. 👉 The functional dependency `StudentID` -> `StudentName` indicates that the `StudentID` attribute uniquely determines the `StudentName` attribute. This means that if we know the `StudentID` for a student, we can also determine their `StudentName`.
- **Closure of Attributes**: The closure of attributes is the process of determining all attributes that can be functionally determined by a given set of attributes.
  - **Example**: Given functional dependencies (A -> B) and (B -> C), attribute closure can deduce (A -> C).

### 8.5 Algorithms for Decomposition
- **Decomposition Algorithm**: Algorithms for decomposition are used to split tables into smaller, more organized tables while preserving functional dependencies.
  - **Example**: A table with attributes (Employee, Department) can be decomposed into separate tables, one for (Employee) and one for (Department).

### 8.6 Decomposition Using Multivalued Dependencies
- **Multivalued Dependencies**: Multivalued dependencies describe relationships where one attribute's values depend on another attribute, but not vice versa.
  - **Example**: In a "StudentCourses" table, "Student" determines "Course," but "Course" does not determine "Student."