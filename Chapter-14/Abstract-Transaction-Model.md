## Abstract Transaction Model:

👉 Concept of transactions and the basic operations involved in moving data between disk and main memory.

👉 Foundational understanding before diving into more complex SQL-based transactions.

- **Focus on Data Movement:**
  - The emphasis here is on when data moves between disk and main memory, excluding SQL insert and delete operations until later.

- **Arithmetic Operations Only:**
  - The language simplifies operations to basic arithmetic. More complex SQL operations will be addressed later.

- **Data Items:**
  - Each data item contains a single value (e.g., a number), identified by a name (A, B, C, etc.).

- **Basic Operations:**
  - Two primary operations: `read(X)` and `write(X)`.
    - `read(X)`: Transfers data item X from the database to a variable (X) in the transaction's main memory buffer.
    - `write(X)`: Transfers the value in the variable X in the main-memory buffer to the data item X in the database.

- **Immediate Database Update:**
  - For simplicity, it's assumed that the `write` operation updates the database immediately. In real systems, this update might be temporarily stored elsewhere before being executed on the disk.

- **Transaction Example (Ti):**
  - A transaction (Ti) is defined to transfer $50 from account A to account B:
    ```
    Ti: read(A);
        A := A - 50;
        write(A);
        read(B);
        B := B + 50;
        write(B).
    ```
    - `read(A)`: Retrieves the value of A from the database to the main memory.
    - `A := A - 50;`: Performs an arithmetic operation in main memory, subtracting 50 from A.
    - `write(A)`: Writes the updated value of A back to the database.
    - `read(B)`: Retrieves the value of B from the database to the main memory.
    - `B := B + 50;`: Performs an arithmetic operation in main memory, adding 50 to B.
    - `write(B)`: Writes the updated value of B back to the database.

## Transaction States and Compensation

👉 Ensuring data integrity and handling failures gracefully.

### Transaction States

- **Initial:** The transaction is created and ready to begin execution.
- **Active:** The transaction is performing its operations on the database.
- **Commit Pending:** The transaction has completed its operations and is waiting for a final decision (commit or abort).
- **Committed:** The transaction has successfully completed and its changes are permanently applied to the database.
- **Aborted:** The transaction has failed and its changes are rolled back, restoring the database to its original state before the transaction began.
- **Compensation Pending:** (Optional) This state signifies the execution of a compensation transaction to undo the effects of a partially committed transaction.
- **Compensated:** (Optional) The compensation transaction has successfully reversed the changes of the failed transaction, leaving the database in a consistent state.

**State Transitions:**

* Initial -> Active: When the transaction begins execution.
* Active -> Commit Pending: When the transaction completes its operations without errors.
* Commit Pending -> Committed: Upon successful commit, making changes permanent.
* Commit Pending -> Aborted: If an error occurs before commit, changes are rolled back.
* Active -> Aborted: If an error occurs during execution, causing immediate rollback.
* Aborted -> Compensation Pending: (Optional) May transition if compensation needed.
* Compensation Pending -> Compensated: After successful execution of compensation logic.
* Compensated -> Aborted: If compensation fails, leaving the database inconsistent.

**Transaction States: Failed and Aborted:**

- **Failed State:**
  - **Trigger:** Hardware or logical errors.
  - **Action:** Rollback to undo changes.
  - **Result:** Moves to the aborted state.

- **Aborted State:**
  - **Options:**
    - **Restart:** For external errors; treated as a new transaction.
    - **Kill:** For internal errors, bad input, or data unavailability.
  - **Outcome:**
    - Restarted transactions are new.
    - Killed transactions terminate due to logical errors or data issues.

### Compensation Transaction

A compensation transaction acts as a "mirror image" of the original transaction, aiming to reverse its effects in case of failure. Consider this example:

* **Original Transaction:**
    * Debits $100 from Account A (payer).
    * Credits $100 to Account B (receiver).
* **Execution:** Both debit and credit operations succeed.
* **Failure:** An error occurs before final commit, invalidating the transfer.

Without compensation, the database remains inconsistent with $100 missing from Account A and appearing unexpectedly in Account B.

**Compensation Transaction:**

* Credits $100 back to Account A.
* Debits $100 from Account B.

The compensation transaction effectively reverses the changes made by the original transaction, restoring the database to its previous consistent state.

**Benefits of Compensation Transactions:**

* Maintain data integrity by ensuring consistency even after failures.
* Improve system reliability by gracefully handling errors.
* Enhance user experience by preventing data loss or corruption.

**Trade-offs:**

* Increased complexity in transaction management.
* Additional overhead for implementing compensation logic.
* Potential performance impact due to extra execution steps.