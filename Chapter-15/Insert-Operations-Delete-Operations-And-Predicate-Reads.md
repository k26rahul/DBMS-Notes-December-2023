## Handling Special Cases in Concurrency Control:

* **Inserts:**
    * **Visibility:** New data may not be immediately visible to other transactions (e.g., "lost insert" problem).
    * **Locking:** May require special locks to prevent phantom reads (inserts after a read but before commit).
* **Deletes:**
    * **Lost updates:** Deleted data may still be seen by ongoing transactions.
    * **Cascading deletes:** Carefully manage dependencies to avoid unintended deletions.
* **Predicate reads:**
    * **Non-repeatable reads:** Data seen initially may disappear before commit due to concurrent deletes.
    * **Index locking:** Optimizes predicate reads by locking only relevant index entries.