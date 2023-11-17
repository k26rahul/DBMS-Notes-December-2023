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
