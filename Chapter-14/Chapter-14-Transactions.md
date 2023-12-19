**Chapter 14: Transactions**

**Transaction Concept**

💡 A transaction is a sequence of one or more SQL statements that are treated as a single unit of work.

- *Properties*: Transactions follow ACID principles – they are Atomic (all-or-nothing), Consistent (maintaining data integrity), Isolated (independent of other transactions), and Durable (persisting changes).
- *Purpose*:
  - Ensures data integrity and consistency.
  - To ensure that our database remains reliable and doesn't end up in a weird state, even if something goes wrong.


**A Simple Transaction Model**

💡 The ABCs of *beginning*, *committing*, and *rolling back* transactions.

A transaction Commences with "Begin Transaction," contains SQL operations, concludes with either "Commit" or "Rollback."

- *Begin Transaction:* This marks the start of a transaction.
- *SQL Statements:*
    - Operations conducted within the transaction.
    - These are the operations or changes you want to make in the database.
- *Commit:*
    - Confirms and applies the changes made by the transaction.
    - When you're sure everything went well, you commit the changes, making them permanent.
- *Rollback:*
    - Reverts the changes made in case of issues.
    - If something goes wrong, you can revert the changes made during the transaction.

**Storage Structure**
- *Transaction Log:* Records all changes made during transactions.
- *Data Storage:* Where the actual data is stored.

**Transaction Atomicity and Durability**
- *Atomicity:* Adheres to the principle of "all or nothing" – either all operations within a transaction succeed, or none.
- *Durability:* Even if the system crashes, your committed transactions will survive.

**Transaction Isolation**

- *Definition:*
  - Guarantees that transactions operate independently, free from interference.
  - 💡 Transactions should be like separate bubbles – they shouldn't interfere with each other.
- **Levels of Isolation:**
  - *Read Uncommitted:* Like peeking into someone else's shopping cart before they've paid.
  - *Read Committed:* You only see the changes that have been officially "checked out."
  - *Repeatable Read:* Prevents others from messing with your data while you're working.
  - *Serializable:* The highest level, ensuring no one can sneak in any changes.

**Serializability**

- *Definition:*
  - Ensures that the outcome of concurrent transactions is equivalent to a serialized execution.
  - 💡 Making sure that even if multiple transactions are happening at once, the end result is as if they happened one after the other.
- *Schedule:* The sequential order of execution for a set of transactions.

**Transaction Isolation and Atomicity**

- *Balancing Act:*
  - Striking a balance between maintaining isolation without compromising atomicity.
  - 💡 Striking the right balance between keeping transactions independent and making sure they all-or-nothing.
- *Isolation vs. Performance:* Delicate considerations for trade-offs.

**Transaction Isolation Levels**
- *Read Uncommitted:* The lowest isolation level.
- *Read Committed:* Guarantees that only committed data is read.
- *Repeatable Read:* Prevents changes to data read during the transaction.
- *Serializable:* The highest isolation level, preventing all anomalies.

**Implementation of Isolation Levels**
- *Locking Mechanisms:*
  - Ensures exclusive access to data during transactions.
  - 💡 Imagine it as taking turns – one transaction locks the data while it's working so others can't barge in.
- *Two-Phase Locking:* Ensures a consistent state throughout the transaction.

**Transactions as SQL Statements**
- *Commands:*
  - BEGIN TRANSACTION, COMMIT, ROLLBACK – these SQL statements control the transaction's flow.
  - 💡 Using SQL to tell the database when to start, commit, or rollback a transaction.
- *SAVEPOINT:*
  - Permits a partial rollback to a specific point in the transaction.
  - 💡 Like bookmarks in a book, letting you jump back to a specific point if needed.

**Transaction States:**

💡 How a transaction moves from one state to another (active, partially committed, committed, failed).

- **Active State:**
  - *Definition:* The starting point when a transaction begins its execution.
  - *Activities:* Transaction is actively performing operations and making changes to the database.
  - *Objective:* To carry out all necessary actions while maintaining ACID properties.

- **Partially Committed State:**
  - *Transition:* When a transaction successfully completes all its operations and is ready to make changes permanent.
  - *Activities:* The transaction awaits confirmation to commit changes.
  - *Objective:* Ensures that the database remains consistent even if the system crashes before the final commitment.

- **Committed State:**
  - *Transition:* Occurs when the system confirms the transaction's changes.
  - *Activities:* Transaction's changes are now permanent and will persist even if there are system failures.
  - *Objective:* Achieves data durability, a key aspect of ACID properties.

- **Failed State:**
  - *Transition:* Triggered by an unexpected error or violation of a constraint during a transaction.
  - *Activities:* Rollback is initiated to undo the changes made by the failed transaction.
  - *Objective:* Maintains the integrity of the database by preventing incomplete or erroneous changes.

**Nested Transactions:**

💡 How transactions can be inside other transactions.

- **Definition:**
  - *Overview:* Transactions within transactions, creating a hierarchy.
  - *Example:* Imagine a bank transaction that involves transferring money and updating an account – each of these could be nested transactions.

- **Savepoints:**
  - *Definition:* Intermediate points within a transaction where you can rollback if needed.
  - *Example:* In a nested transaction, a savepoint could mark a point where changes are accepted, and if an issue arises later, only the changes from that savepoint onward are rolled back.

- **Commit and Rollback in Nested Transactions:**
  - *Commit:* Only affects the changes made in the innermost transaction, ensuring changes in outer transactions remain tentative until the outermost commit.
  - *Rollback:* Reverts changes made in the innermost transaction, with the option to revert changes up to a specific savepoint.

**Concurrency Control:**

💡 Managing multiple transactions happening at the same time.

- **Definition:**
  - *Overview:* Managing multiple transactions executing simultaneously to ensure consistency and avoid conflicts.
  - *Challenge:* Preventing issues like data inconsistency, lost updates, or conflicts when multiple transactions access and modify the same data.

- **Locking Mechanisms:**
  - *Purpose:* Ensures exclusive access to data during a transaction to avoid conflicts.
  - *Example:* If Transaction A is updating a record, Transaction B might have to wait until A finishes to avoid conflicting changes.

- **Isolation Levels in Concurrency Control:**
  - *Read Uncommitted:* Allows transactions to read uncommitted changes, risking dirty reads.
  - *Read Committed:* Transactions can only read committed changes, reducing the risk of dirty reads.
  - *Repeatable Read and Serializable:* Provide higher levels of isolation, preventing various anomalies but may impact performance.

- **Timestamp-based Concurrency Control:**
  - *Overview:* Assigns a unique timestamp to each transaction, determining the order of execution.
  - *Advantage:* Helps avoid conflicts and ensures a consistent order of operations.

- **Deadlocks:**
  - *Definition:* Situations where two or more transactions are unable to proceed because each is waiting for the other to release a lock.
  - *Resolution:* Requires a deadlock detection and resolution mechanism to break the deadlock and allow transactions to continue.