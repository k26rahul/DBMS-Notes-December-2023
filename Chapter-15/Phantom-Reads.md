### Phantom Reads

A "phantom read" occurs when a transaction sees a set of records that match a certain condition, but as the transaction progresses, another transaction modifies the database, causing the initial condition to produce a different set of records upon re-evaluation.

#### Example:

1. **Initial Transaction T1**:
   - T1 reads all records where the "Status" is "Pending."
   - It finds and processes records A, B, and C.

2. **Concurrent Transaction T2**:
   - T2 inserts a new record D with the "Pending" status.

3. **Subsequent Transaction T1**:
   - T1 re-executes the same query, expecting to process only records A, B, and C.
   - However, it now also includes the newly inserted record D, which wasn't there during the initial read.

#### Key Points:

- Phantom reads involve unexpected changes in the dataset during a transaction's execution.
- These inconsistencies can lead to unintended consequences, especially in scenarios where data integrity is crucial.
- Isolation levels, such as SERIALIZABLE, are often employed to minimize the occurrence of phantom reads by ensuring a higher level of transaction isolation.
