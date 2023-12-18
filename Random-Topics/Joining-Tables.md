### Joining Tables:

In a relational database, you often have multiple tables, and you might need to combine information from different tables. This is where **joins** come in.

https://en.m.wikipedia.org/wiki/Join_(SQL)

https://en.m.wikipedia.org/wiki/Hash_join

#### Types of Joins:

1. **Inner Join:**
   - Retrieves rows from both tables where there is a match based on a specified condition (usually equality of a column).

2. **Outer Join (Left, Right, Full Outer):**
   - Retrieves matching rows as well as non-matching rows from one or both tables.

### Nested Loop Join (Traditional Join):

In a **nested loop join**, each row from the first table is paired with every row from the second table to find matches. It's like a nested loop in programming:

#### Example:
```
Table A                        Table B
| ID | Name   |                 | ID | Age |
|----|--------|                 |----|-----|
| 1  | Alice  |                 | 2  | 25  |
| 2  | Bob    |                 | 1  | 30  |
| 3  | Charlie|                 | 4  | 22  |
```

With a nested loop join, you compare every combination of rows from Table A with Table B:


```
| ID | Name   | ID | Age |
|----|--------|----|-----|
| 1  | Alice  | 2  | 25  |  (Comparison)
| 1  | Alice  | 1  | 30  |  (Comparison, matched*)
| 1  | Alice  | 4  | 22  |  (Comparison)
| 2  | Bob    | 2  | 25  |  (Comparison, matched*)
| 2  | Bob    | 1  | 30  |  (Comparison)
| 2  | Bob    | 4  | 22  |  (Comparison)
| 3  | Charlie| 2  | 25  |  (Comparison)
| 3  | Charlie| 1  | 30  |  (Comparison)
| 3  | Charlie| 4  | 22  |  (Comparison)
```

### Hash Join:

Now, consider a **hash join**:

#### Example Tables:
```
Table A                        Table B
| ID | Name   |                 | ID | Age |
|----|--------|                 |----|-----|
| 1  | Alice  |                 | 2  | 25  |
| 2  | Bob    |                 | 1  | 30  |
| 3  | Charlie|                 | 4  | 22  |
```

#### Hashing Phase:
Hash tables are created for both tables based on a specific column (e.g., ID).

#### Partitioning:
Rows are hashed and placed into partitions based on the hash values.

#### Probing and Comparison:
Only tuples with the same hash code are considered for comparison:

```
| ID | Name   | Age |
|----|--------|-----|
| 1  | Alice  | 30  |  (Comparison, matched*)
| 2  | Bob    | 25  |  (Comparison, matched*)
```

### Conclusion:

- **Nested Loop Join:** Compares every combination of rows.
- **Hash Join:** Uses hashing to efficiently identify and compare only potentially matching rows.

👉 Joins are fundamental to relational databases, allowing you to extract meaningful information by combining data from different tables based on common attributes.
👉 Hash joins provide a more efficient way of achieving this by leveraging hashing techniques.