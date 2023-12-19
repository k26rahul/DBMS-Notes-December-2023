## Multiversion Schemes

Multiversion concurrency control (MVCC) is a technique used in databases to manage concurrent access to data by maintaining multiple versions of the same data item. This allows multiple transactions to read and write data simultaneously without conflicting with each other.

**Core Idea:**

* Instead of locking data items, MVCC keeps track of historical versions alongside the current one.
* Transactions operate on their own versions, isolated from changes made by other transactions.

**Benefits:**

* **Increased Concurrency:** Transactions don't block each other, leading to smoother performance and higher throughput.
* **Improved Read Scalability:** Reads can access any version of the data, regardless of ongoing writes.
* **Simplified Conflict Resolution:** Conflicts are automatically detected and resolved based on version timestamps.

**Types of MVCC:**

* **Snapshot Isolation:** Each transaction sees a consistent snapshot of the database at the time it starts.
* **Read Committed Isolation:** Transactions see the latest committed versions of data items.

**Implementation:**

* Versioning can be implemented through various techniques like copy-on-write or timestamping.
* Databases manage garbage collection of old versions to optimize storage space.