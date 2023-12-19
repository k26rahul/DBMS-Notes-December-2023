## Storage Structure

Storage media is categorized into volatile, nonvolatile, and stable storage:

- **Volatile Storage:**
  - Data in volatile storage (e.g., main memory, cache) is fast but doesn't survive system crashes.

- **Nonvolatile Storage:**
  - Data in nonvolatile storage (e.g., magnetic disks, flash storage) survives crashes but is slower, especially for random access. Still, it's susceptible to failures.

- **Stable Storage:**
  - Information in stable storage is theoretically never lost. It's achieved by replicating data in several nonvolatile storage media (usually disks) with independent failure modes. Updates must be carefully executed to avoid information loss.

- **Practical Considerations:**
  - Real-world systems may blur these distinctions. Some systems, like certain RAID controllers, offer battery backup for main memory, blurring the line between volatile and nonvolatile storage.

- **Durability and Atomicity:**
  - For a transaction to be durable (changes survive), they must be written to stable storage. Atomicity requires log records to be written to stable storage before any database changes. The effectiveness of these guarantees depends on the robustness of the stable storage implementation.

- **Multiplicity in Storage Copies:**
  - Highly valuable data may require multiple copies or a closer approximation of stable storage, ensuring data resilience even in the face of failures.