🚨🚨🚨 Removed from December syllabus 🚨🚨🚨

## 15.4 Timestamp-Based Protocols

- Timestamp-based protocols are concurrency control mechanisms that use timestamps to order transactions.
- Each transaction is assigned a unique timestamp when it is submitted to the system.
- This timestamp is used to determine the order in which transactions are executed and to ensure that the database remains consistent even when multiple transactions are executing concurrently.

### Concurrency Control with Timestamps

There are two main aspects of concurrency control with timestamps:

* **Timestamp Ordering:** Transactions are executed in order of their timestamps. This means that a transaction with an older timestamp will always be executed before a transaction with a younger timestamp.
* **Conflict Serializability:** Even though multiple transactions may be executing concurrently, the outcome must be equivalent to some serial execution of the transactions. This means that any conflicts between transactions must be resolved in a way that maintains the consistency of the database.

To ensure conflict serializability, timestamp-based protocols typically use one of the following two approaches:

* **Timestamp-Based Locking:** In this approach, a transaction acquires a lock on a data item before it can read or write the item. The type of lock that is required depends on the operation that the transaction is performing. For example, a read operation requires a shared lock, while a write operation requires an exclusive lock. A transaction can only acquire a lock on a data item if its timestamp is older than any other transaction that has the item locked. This prevents conflicting transactions from interleaving their operations on the same data item.
* **Optimistic Timestamp-Based Concurrency Control (OTCC):** In this approach, no locking is used during transaction execution. Instead, conflicts are detected and resolved at commit time. When a transaction attempts to commit, it is checked to see if it conflicts with any other transactions that have already committed. If a conflict is found, the transaction with the younger timestamp is aborted.

### Examples of Timestamp-Based Protocols

Here are two examples of timestamp-based protocols:

* **Thomas's Write Rule:** This protocol is a timestamp-based locking protocol that uses timestamps to order write operations. Under Thomas's Write Rule, a transaction can only write a data item if its timestamp is older than the timestamps of all other transactions that have written the item. This prevents write conflicts and ensures that writes are serialized in timestamp order.
* **Timestamp-Based OCC (Optimistic Concurrency Control):** This protocol is an optimistic timestamp-based protocol that does not use any locking. Instead, conflicts are detected and resolved at commit time. When a transaction attempts to commit, it is checked to see if it conflicts with any other transactions that have already committed. If a conflict is found, the transaction with the younger timestamp is aborted.

### Advantages and Disadvantages of Timestamp-Based Protocols

- 😍 Timestamp-based protocols are well-suited for workloads that are dominated by read operations and can avoid deadlocks.
- 🤔 However, they can also lead to more aborts than locking-based protocols, especially for write-heavy workloads.

**Advantages:**

* **Simplicity:** They are relatively simple to implement and understand.
* **Efficiency:** They can be very efficient for workloads that are dominated by read operations.
* **Deadlock Avoidance:** They can avoid deadlocks, which are a common problem with locking-based concurrency control protocols.

**Disadvantages:**

* **Aborts:** They can lead to more aborts than locking-based protocols, especially for write-heavy workloads. This is because conflicts are not detected until commit time, which can mean that a significant amount of work may be wasted if a transaction is aborted.
* **Overhead:** Maintaining timestamps and checking for conflicts can add some overhead to the system.