## Transaction

A transaction in a database is like a single unit of work that can involve one or more operations. It follows the ACID principles, ensuring that the operations are Atomic (all-or-nothing), Consistent (maintaining data integrity), Isolated (independent of other transactions), and Durable (persisting changes).

**SQL Representation of a Transaction:**

In SQL, a transaction typically involves three main commands:

- **BEGIN TRANSACTION:** Marks the start of a transaction.
- **SQL Statements:** Operations or changes made to the database.
- **COMMIT:** Confirms and applies the changes, making them permanent.

If something goes wrong during the transaction, you can use:

- **ROLLBACK:** Reverts the changes made, ensuring the database returns to its previous state.

## Example Scenario of a Financial Transaction:

Consider a scenario where $100 is being transferred from Account A to Account B with intermediary steps.

🚨🚨🚨 Removed from December syllabus 🚨🚨🚨

1. **Begin Transaction:**
   ```sql
   BEGIN TRANSACTION;
   ```

2. **Deduct from Account A:**
   ```sql
   UPDATE Accounts SET Balance = Balance - 100 WHERE AccountNumber = 'A';
   ```

3. **Temporary Hold for Verification:**
   ```sql
   INSERT INTO TransactionLog (TransactionType, Amount, Description) VALUES ('Hold', 100, 'Verification');
   ```

4. **Add to Account B (Temporarily):**
   ```sql
   UPDATE Accounts SET Balance = Balance + 100 WHERE AccountNumber = 'B';
   ```

5. **Finalize Transaction:**
   ```sql
   UPDATE TransactionLog SET TransactionType = 'Transfer' WHERE Description = 'Verification';
   ```

6. **Commit Transaction:**
   ```sql
   COMMIT;
   ```

7. **Rollback on Failure (if needed):**
   ```sql
   ROLLBACK;
   ```

Diagram representing the steps in the financial transaction:

```
  Begin Transaction
        |
  Deduct from A
        |     |
        |   Rollback (if needed)
        |
    Hold for Verification
        |               |
    Add to B -----> Rollback (if needed)
        |
    Finalize Transaction
        |              |
      Commit      Rollback (if needed)
```