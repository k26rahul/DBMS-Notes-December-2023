- Hash Join

  - Join algorithm in databases
  - Hash tables used for efficiency
  - Suitable for large datasets
  - Divides data into buckets
  - Compares and combines matching data
  - Faster than nested loop join
  - Common in query optimization
  - Parallel processing support

- Hash Join Workflow

  - **Build Phase:**
    - Smaller table (build input) is read.
    - Hash function applied, data placed in buckets.
    - Hash table created.
  - **Probe Phase:**
    - Larger table (probe input) is read.
    - Hash function applied to each row.
    - Matching rows found in the hash table.
    - Results combined for final output.
  - Efficient for large datasets.


# An example:


**Scenario**:
- The "Employees" table contains information about employees in a company, including their names and the department they work in.
- The "Departments" table lists various departments within the company.

Here are the two tables:

**Employees Table**:

| EmployeeID | EmployeeName | DepartmentID |
|------------|--------------|--------------|
| 1          | Alice        | 101          |
| 2          | Bob          | 102          |
| 3          | Carol        | 103          |
| 4          | David        | 102          |
| 5          | Emma         | 101          |

**Departments Table**:

| DepartmentID | DepartmentName |
|--------------|----------------|
| 101          | HR             |
| 102          | Finance        |
| 103          | Marketing      |

Now, let's perform a hash join to combine these two tables based on the "DepartmentID." The goal is to create a new table that shows the employee names along with their respective department names.

Here's how the hash process works:

1. **Partitioning Tables**: The input tables (in our case, "Employees" and "Departments") are divided into separate hash buckets. Each row from the tables is assigned to a hash bucket based on the hash value calculated for a specific column, such as "DepartmentID."

2. **Hash Value Calculation**: The hash function takes the value of the chosen column, like "DepartmentID," and applies a mathematical transformation to it. This transformation generates a hash value, which is used to determine which hash bucket the row belongs to. The hash function is designed to distribute data evenly across the hash buckets.

3. **Matching Hash Buckets**: Rows with the same hash value are placed in the same hash bucket in both tables. This is the key to the hash join's efficiency; it allows the system to quickly identify matching rows in different tables by comparing hash values instead of directly scanning each row.

4. **Combining Rows**: After matching hash buckets are identified, rows from the corresponding hash buckets are combined to create the result set. This result set contains the data from both tables based on the matching hash values.

**Resulting Table**:

| EmployeeName | DepartmentName |
|--------------|----------------|
| Alice        | HR             |
| Bob          | Finance        |
| Carol        | Marketing      |
| David        | Finance        |
| Emma         | HR             |

In this result table, the hash join combined information from the "Employees" and "Departments" tables based on the "DepartmentID." Each employee is matched with their respective department, and you have a clear view of which employee works in which department.