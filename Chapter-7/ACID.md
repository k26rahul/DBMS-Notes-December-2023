**ACID in Financial Transactions**

**A** - **Atomicity**
   - All parts of a transaction succeed or fail together.
   - Example: When transferring money from one account to another, either the entire transfer happens or none of it does.

**C** - **Consistency**
   - The database starts in a consistent state and ends in a consistent state.
   - Example: If an account has $100, a withdrawal cannot leave it with a negative balance.

**I** - **Isolation**
   - Transactions are independent of each other until they're completed.
   - Example: If two people try to withdraw from the same account simultaneously, one should not see the other's changes until they're both done.

**D** - **Durability**
   - Once a transaction is committed, its changes are permanent, even in the face of system crashes.
   - Example: After you deposit money, it will still be there even if the bank's computer crashes.
