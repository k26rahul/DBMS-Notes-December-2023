## What are mapping cardinalities and why are they used? Discuss their types in brief with suitable diagrams.

- Mapping cardinalities refer to the relationship between entities in a database model, specifying how instances of one entity relate to instances of another entity.
- These cardinalities help define the nature and constraints of relationships in a database.

- Types of Mapping Cardinalities:
   - One-to-One (1:1)
   - One-to-Many (1:N)
   - Many-to-Many (N:M)

## What are the Mobile App constraints? Illustrate the typical architecture of a mobile app with a suitable diagram.

**Mobile App Constraints:**
1. Limited Resources:
   - Limited processing, memory, and battery.

2. Network Variability:
   - Unpredictable network conditions.

3. Device Fragmentation:
   - Diverse devices, screen sizes, and capabilities.

4. Security Concerns:
   - Vulnerable to breaches and unauthorized access.

**Typical Mobile App Architecture:**
```
+---------------------------+
| Presentation Layer (UI)   |
+---------------------------+
| Application Layer (Logic) |
+---------------------------+
| Data Layer (Backend)      |
+---------------------------+
```
- **Presentation Layer:** User interface.
- **Application Layer:** Logic and processing.
- **Data Layer:** Manages storage and communication.

## Explain in brief the ways in which caching could be used to speed up Web server performance.

**Caching for Web Server Performance:**

- **Browser Caching:**
  - Store static resources (CSS, JS, images) in the browser cache.
  - Reduces server requests, improves load times for returning visitors.

- **Content Delivery Network (CDN):**
  - Distribute content across geographically distributed servers.
  - Caches content closer to users, reducing latency.

- **Object Caching:**
  - Cache database query results or frequently used objects.
  - Reduces repeated processing, speeds up dynamic content delivery.

- **Page Caching:**
  - Cache entire HTML pages.
  - Minimizes server processing for frequently accessed pages.

- **Reverse Proxy Caching:**
  - Use a reverse proxy server to cache content.
  - Offloads server, improves response times for repeated requests.

## Redundant array of independent disks forms a major part in the storage structure of databases. Discuss this concept and compare its levels.

[./Random-Topics/RAID.md](./Random-Topics/RAID.md)

**RAID (Redundant Array of Independent Disks):**

1. **RAID 0 (Striping):**
   - *Advantage:* Improved speed.
   - *Disadvantage:* No redundancy; data loss if one drive fails.

2. **RAID 1 (Mirroring):**
   - *Advantage:* High redundancy.
   - *Disadvantage:* Higher cost; write performance similar to a single drive.

3. **RAID 5 (Striping with Parity):**
   - *Advantage:* Balanced read/write performance.
   - *Disadvantage:* Fault tolerance limited to one drive failure.

4. **RAID 10 (Combination of RAID 1 and RAID 0):**
   - *Advantage:* High redundancy and performance.
   - *Disadvantage:* Costlier; can tolerate specific drive failures.

5. **RAID 6 (Striping with Dual Parity):**
   - *Advantage:* Enhanced fault tolerance.
   - *Disadvantage:* Slightly lower write performance.

Choose based on needs: speed (RAID 0), redundancy (RAID 1), balance (RAID 5), or a mix (RAID 10/6).

## Considering the abstract transaction model:
a) Illustrate the state diagram of a transaction and elaborate on its states
b) Discuss a compensation transaction with an example

**a) Transaction State Diagram:**

```
Active ----> Partially Committed ----> Committed
  |
  v
Failed
  |
  v
Aborted
```

- **States:**
  1. **Active:**
     - Transaction is executing.
     - May read and write data.

  2. **Partially Committed:**
     - Transaction completed execution.
     - Awaits final commitment or rollback.

  3. **Committed:**
     - Changes made by the transaction are permanent.
     - Transaction successfully completed.

  4. **Failed:**
     - An error occurred during execution.
     - Must be rolled back to maintain consistency.

  5. **Aborted:**
     - Transaction rolled back.
     - Returns the database to its state before transaction execution.

**b) Compensation Transaction:**

- **Definition:**
  - Used to undo the effects of a previously committed transaction.

- **Example:**
  - **Scenario:**
    - Money transfer from account A to B.
  - **Compensation Transaction:**
    - If transfer fails after deducting from A, a compensation transaction adds the amount back to A or ensures an equivalent action.
  - **Purpose:**
    - Maintain data consistency despite transaction failure.