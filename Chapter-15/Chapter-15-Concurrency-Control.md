## Chapter-15: Concurrency Control

💡 Concurrency control ensures smooth, conflict-free execution of multiple database transactions by managing simultaneous access.

In a multi-user database environment, multiple transactions can be executing concurrently, and without proper control mechanisms, this concurrent execution can lead to various issues such as data inconsistencies, conflicts, and potential loss of data integrity. The primary goals of concurrency control are to ensure data consistency, isolation between transactions, and to maintain the integrity of the database despite concurrent execution.

### Key aspects and goals of concurrency control:

1. **Consistency:** Concurrency control aims to maintain the consistency of the database despite concurrent execution of transactions. This involves ensuring that the database transitions from one consistent state to another, and the final result is as if transactions were executed in some serial order.

2. **Isolation:** Transactions should execute in isolation from each other, meaning the intermediate state of a transaction should be hidden from other transactions until it is committed. This isolation prevents one transaction from interfering with the execution of another.

3. **Serializability:** The execution of concurrent transactions should be equivalent to some serial order of their execution. Even though transactions may execute concurrently, their overall effect on the database should be as if they were executed one after the other.

5. **Locking Mechanisms:** One common approach to achieve concurrency control is through the use of locks. Transactions request and release locks on data items to control access. Locks can be of various types, such as shared locks (for read access) and exclusive locks (for write access). Two-Phase Locking (2PL) is a widely used locking protocol.

4. **Deadlock Prevention and Detection:** Concurrency control systems often include mechanisms to prevent and detect deadlocks. A deadlock occurs when transactions are waiting for each other to release locks, resulting in a cyclic waiting situation. Preventing deadlocks and resolving them when detected are essential for maintaining system stability.

6. **Timestamp-Based Schemes:** 🚨🚨🚨 Removed from December syllabus 🚨🚨🚨 Another approach involves assigning timestamps to transactions and using these timestamps to determine the order of execution. Older transactions may be given precedence, ensuring a consistent order of execution.

7. **Multiversion Schemes:** 🚨🚨🚨 Removed from December syllabus 🚨🚨🚨 Some systems maintain multiple versions of data items to allow transactions to work with a snapshot of the database at their start time. This approach is particularly useful for read operations.

8. **Validation-Based Protocols:** Transactions validate their changes against the current state of the database before committing. Read-only transactions validate against the most recent committed transaction.

9.  **Snapshot Isolation:** Transactions see a consistent snapshot of the database, providing a higher level of isolation without the need for locking.

### 15.1 Lock-Based Protocols
  - **Locks:**
    - Mechanism for controlling access to shared data.
  - **Two-Phase Locking (2PL):**
    - Transactions acquire all required locks before executing and release them only after completion.
  - **Types of Locks:**
    - Shared locks for read access, exclusive locks for write access.
  - **Phases of 2PL:**
    - Growing Phase: Acquiring locks.
    - Shrinking Phase: Releasing locks.

### 15.2 Deadlock Handling

Sometimes, transactions get stuck waiting for each other's locks, creating a deadlock (think two kids holding onto each other's swings). We need to:

* **Detect:** Regularly check for "waiting circles" in the lock usage map.
* **Prevent:** Assign priorities or use timestamps to avoid circular dependencies.
* **Resolve:** As a last resort, break the deadlock by aborting one transaction.

- **Handling Deadlocks:**
  - *Detection:*
    - Periodic checks for cycles in the wait-for graph.
  - *Prevention:*
    - Assign priorities to transactions or use timestamps.
  - *Avoidance:*
    - Banker's algorithm for safe state.
  - *Resolution:*
    - Abort one or more transactions to break the deadlock.

### 15.3 Multiple Granularity

🚨🚨🚨 Removed from December syllabus 🚨🚨🚨

Going Granular: Different Lock Sizes for Different Needs ️☑️

Not all data deserves the same level of attention. Imagine locking an entire market just to buy a single apple! We have:

* **Fine-grained locking:** Lock individual items (apples) for precision.
* **Coarse-grained locking:** Lock groups of items (fruit baskets) for efficiency.

- **Introduction to Multiple Granularity:**
  - Transactions may need to lock different levels of data granularity.

- **Lock Compatibility Matrix:**
  - Defines which locks are compatible with others to avoid conflicts.

- **Multiple Granularity Locking:**
  - Allows locking at various levels, from the entire database down to individual records.

### 15.4 Timestamp-Based Protocols

🚨🚨🚨 Removed from December syllabus 🚨🚨🚨

- **Introduction to Timestamp-Based Protocols:**
  - Uses timestamps to order transactions.

- **Concurrency Control with Timestamps:**
  - **Timestamp Ordering:**
    - Older transactions get precedence.
  - **Conflict Serializability:**
    - Transactions' order must be conflict-serializable to ensure consistency.

### 15.5 Validation-Based Protocols

Validation Before Commitment: Double-Checking Before Publishing ☑️

Transactions validate their changes against the current database state before finalizing (like proofreading before publishing a book).

- **Introduction to Validation-Based Protocols:**
  - Transactions validate before committing.

- **Concurrency Control with Validation:**
  - **Read-Only Transactions:**
    - Validate against the most recent committed transaction.
    - 💡 They simply check against the latest committed version.
  - **Read-Write Transactions:**
    - Validate against all transactions that started before the current transaction.
    - 💡 They need to ensure no conflicting changes occurred since they started.

### 15.6 Multiversion Schemes

🚨🚨🚨 Removed from December syllabus 🚨🚨🚨

🤔🍃⭐ Imagine having multiple copies of a book, each representing a different edition. Multiversion schemes store snapshots of data items, allowing transactions to work with their own version without conflicts. It's like everyone reading/editing their preferred edition simultaneously.

- **Introduction to Multiversion Schemes:**
  - Maintain multiple versions of a data item to allow for concurrent transactions.

- **Concurrency Control with Multiversion Schemes:**
  - Each transaction works with its snapshot of the database.

### 15.7 Snapshot Isolation

🤔🍃⭐ Transactions see a consistent picture of the database at their start time, unaffected by ongoing changes. It's like everyone getting a frozen image of the market at the moment they entered.

- **Introduction to Snapshot Isolation:**
  - Transactions see a consistent snapshot of the database, ensuring isolation.

- **Concurrency Control with Snapshot Isolation:**
  - Transactions do not interfere with each other, enhancing concurrency.

### 15.8 Insert Operations, Delete Operations, and Predicate Reads

- **Handling Special Cases:**
  - Inserting, deleting, and searching based on specific conditions (predicates) require special handling in a concurrent environment. We need clever algorithms to ensure data integrity and consistency.

### Beyond the Perfect Picture: Weak Consistency for Scalability

🚨🚨🚨 Removed from December syllabus 🚨🚨🚨

Sometimes, perfect consistency takes a backseat for performance and scalability. Weak consistency models relax the rules:

* **Eventual Consistency:** All replicas of the data will eventually converge to the same state, like news eventually reaching everyone in the market, even if with slight delays.
* **Causal Consistency:** The order of operations is preserved, ensuring cause-and-effect relationships remain clear, like knowing which transaction updated a price tag before another transaction reacted to it.

### 15.10 Concurrency in Index Structures

- **Concurrency Control in Index Structures:**
  - Challenges and solutions for maintaining consistency in index structures when accessed concurrently.
