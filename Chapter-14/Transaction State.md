**a) Transaction State Diagram:**

```
Active ----> Partially Committed ----> Committed
  |
  v
Failed
  |
  v
Aborted
```

- **States:**
  1. **Active:**
     - Transaction is executing.
     - May read and write data.

  2. **Partially Committed:**
     - Transaction completed execution.
     - Awaits final commitment or rollback.

  3. **Committed:**
     - Changes made by the transaction are permanent.
     - Transaction successfully completed.

  4. **Failed:**
     - An error occurred during execution.
     - Must be rolled back to maintain consistency.

  5. **Aborted:**
     - Transaction rolled back.
     - Returns the database to its state before transaction execution.

**b) Compensation Transaction:**

- **Definition:**
  - Used to undo the effects of a previously committed transaction.

- **Example:**
  - **Scenario:**
    - Money transfer from account A to B.
  - **Compensation Transaction:**
    - If transfer fails after deducting from A, a compensation transaction adds the amount back to A or ensures an equivalent action.
  - **Purpose:**
    - Maintain data consistency despite transaction failure.