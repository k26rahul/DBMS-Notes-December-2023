**Decomposition Using Functional Dependencies - Example**

**Original Table:**

| StudentID | StudentName | CourseID | CourseName     | Instructor  | Credits | EnrollmentDate | Grade |
|-----------|------------|----------|----------------|------------|---------|----------------|-------|
| 1         | Alice      | 101      | Math 101       | Prof. Smith | 4       | 2023-01-15     | A     |
| 1         | Alice      | 201      | Physics 201    | Prof. Johnson | 3      | 2023-02-10     | B     |
| 2         | Bob        | 101      | Math 101       | Prof. Smith | 4       | 2023-01-15     | C     |
| 2         | Bob        | 202      | Chemistry 202  | Prof. White | 3       | 2023-02-05     | A     |
| 3         | Carol      | 201      | Physics 201    | Prof. Johnson | 3      | 2023-02-10     | A     |

**Decomposed Tables:**

1. **Students:**

   | StudentID | StudentName |
   |-----------|------------|
   | 1         | Alice      |
   | 2         | Bob        |
   | 3         | Carol      |

2. **Courses:**

   | CourseID | CourseName     | Instructor  | Credits |
   |----------|----------------|------------|---------|
   | 101      | Math 101       | Prof. Smith | 4       |
   | 201      | Physics 201    | Prof. Johnson | 3      |
   | 202      | Chemistry 202  | Prof. White | 3       |

3. **Enrollments:**

   | StudentID | CourseID | EnrollmentDate | Grade |
   |-----------|----------|----------------|-------|
   | 1         | 101      | 2023-01-15     | A     |
   | 1         | 201      | 2023-02-10     | B     |
   | 2         | 101      | 2023-01-15     | C     |
   | 2         | 202      | 2023-02-05     | A     |
   | 3         | 201      | 2023-02-10     | A     |