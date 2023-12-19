## Abstract Transaction Model: Transaction States and Compensation

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