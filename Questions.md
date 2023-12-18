### What are mapping cardinalities and why are they used? Discuss their types in brief with suitable diagrams.

- Mapping cardinalities refer to the relationship between entities in a database model, specifying how instances of one entity relate to instances of another entity.
- These cardinalities help define the nature and constraints of relationships in a database.

- Types of Mapping Cardinalities:
   - One-to-One (1:1)
   - One-to-Many (1:N)
   - Many-to-Many (N:M)

### What are the Mobile App constraints? Illustrate the typical architecture of a mobile app with a suitable diagram.

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

### Explain in brief the ways in which caching could be used to speed up Web server performance.

**Caching for Web Server Performance:**

1. **Page Caching:**
   - Store entire web pages to reduce server processing time.

2. **Object Caching:**
   - Cache specific components like images to accelerate resource loading.

3. **Content Delivery Network (CDN):**
   - Distribute cached content globally to reduce latency for users.

4. **Browser Caching:**
   - Instruct browsers to store local copies, speeding up page rendering.