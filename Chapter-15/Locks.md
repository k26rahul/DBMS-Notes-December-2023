💡 **Concurrency control ensures data consistency** by managing the simultaneous execution of multiple transactions in a database.

💡 **Locks and protocols play a crucial role in managing simultaneous access**, providing a structured approach to prevent conflicts and maintain the integrity of the data.

💡 **Deadlock prevention strategies are essential** to minimize disruptions in the database environment and ensure smooth transaction processing.

## Locks
- **Definition**: Locks serve as a fundamental mechanism to control access to data within a database system. Preventing data inconsistencies that may arise when multiple transactions attempt to access the same data simultaneously.
- **Types**:
  - **Shared Lock (S)**: This type of lock allows multiple transactions to read the same data concurrently, ensuring that no transaction can modify the data until all shared locks are released.
  - **Exclusive Lock (X)**: On the other hand, an exclusive lock grants exclusive access to a transaction, preventing other transactions from either reading or writing to the data.

## Lock Protocols
1. **Two-Phase Locking (2PL)**
   - **Phases**:
     - **Growing Phase**: Transactions acquire the necessary locks during this phase, ensuring that they have the required permissions to access the data.
     - **Shrinking Phase**: Once a transaction releases a lock, it cannot acquire any additional locks. This phase prevents inconsistencies by maintaining a strict order of lock acquisition and release.
   - **Rule**: The fundamental rule of 2PL is to avoid any unlock operation before all required locks are acquired. This ensures a consistent and predictable transaction flow.

2. **Strict Two-Phase Locking**
   - **Extension of 2PL**: This protocol takes the principles of 2PL a step further.
   - **Rule**: In strict two-phase locking, no unlock operation is permitted until the transaction is ready to commit. This ensures that no changes are made to the database until the transaction is certain to be successful.

3. **Timestamp-Based Protocols**
   - **Assign a timestamp to each transaction**: Timestamp-based protocols use a systematic approach to manage the order of transactions.
   - **Rules**:
     - Read only if the transaction's timestamp is earlier than the item's write timestamp.
     - Write only if the transaction's timestamp is later than the item's read and write timestamps. This approach guarantees a logical and consistent sequence of data access.

## Deadlocks
- **Definition**: A deadlock occurs when two or more transactions cyclically wait for resources held by each other, resulting in a standstill.
- **Prevention Strategies**:
  - **Timeouts**: Transactions that take an excessive amount of time are automatically aborted, preventing potential deadlocks.
  - **Wait-Die and Wound-Wait Schemes**:
    - **Wait-Die**: Older transactions wait for younger ones, but if a younger transaction requests an older transaction's locked data, the older transaction is aborted to resolve the deadlock.
    - **Wound-Wait**: Younger transactions wait for older ones, but if an older transaction requests a younger transaction's locked data, the younger transaction is aborted to break the deadlock.
  - **Graph-Based Approaches**: By modeling the dependencies between transactions as a graph, it becomes possible to detect and break deadlock cycles proactively.

# Real life examples:

## Locks
- **Definition**: Locks serve as a fundamental mechanism to control access to data within a database system.
- **Types**:
  - **Shared Lock**: Imagine a library scenario where multiple students can read the same book simultaneously. Each student has a shared lock on the book, ensuring no one can modify its content until all students are done.
  - **Exclusive Lock**: Picture a reserved study room in the library. Only one student can use it at a time, granting exclusive access and preventing others from reading or writing within the room.

## Lock Protocols
1. **Two-Phase Locking (2PL)**
   - **Phases**:
     - **Growing Phase**: Think of acquiring books from the library shelves. As a student, you must acquire locks on the books you need before starting your study session.
     - **Shrinking Phase**: Returning the books signifies the shrinking phase, where you release the locks to allow others to access the books. This strict order of acquisition and release prevents inconsistencies.
   - **Rule**: Just like in the library, no unlocking is allowed until all the required locks are acquired, ensuring a predictable and consistent transaction flow.

2. **Strict Two-Phase Locking**
   - **Extension of 2PL**: This is akin to a study group in the library. No changes, such as notes or annotations, are allowed in the shared resources until the group is ready to commit those changes collectively.
   - **Rule**: Similar to the strict policy in a study group, no unlocking occurs until the transaction is ready to commit, ensuring the success of the entire group.

3. **Timestamp-Based Protocols**
   - **Assign a timestamp to each transaction**: Think of timestamps as reservation times for study rooms in a busy library. The rules ensure that students can only read or write in a reserved room during their allocated time slots. This systematic approach guarantees a logical and consistent sequence of data access.

## Deadlocks
- **Definition**: A deadlock is comparable to a scenario where two students are holding each other's reserved books, and they both need the other's book to complete their study.
- **Prevention Strategies**:
  - **Timeouts**: Imagine a librarian noticing students taking too long in a study room. The librarian automatically interrupts and asks them to leave, preventing potential deadlocks.
  - **Wait-Die and Wound-Wait Schemes**:
    - **Wait-Die**: In a library, older students patiently wait for younger ones, but if a younger student requests a book held by an older student, the older student is asked to leave, resolving the deadlock.
    - **Wound-Wait**: Picture a scenario where younger students are willing to wait for older ones. However, if an older student requests a book held by a younger student, the younger student is asked to leave, breaking the deadlock.
  - **Graph-Based Approaches**: Think of a librarian observing the flow of book requests and interventions to break any cyclic dependencies. By modeling the dependencies between transactions as a graph, it becomes possible to detect and break deadlock cycles proactively.
