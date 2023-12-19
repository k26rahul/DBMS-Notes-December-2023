**Caching in DBMS**

**What is Caching?**

- Caching is a technique in DBMS that speeds up performance by storing often-used data temporarily for **quicker access** and **reduced load on the main database**.

**Terminologies:**

1. **Cache:** A small, fast storage area that holds a portion of main database data.

2. **Cache Hit:** When needed data is found in the cache, it's a hit, making retrieval faster.

   Example: Getting customer information from the cache instead of the database.

3. **Cache Miss:** If the data isn't in the cache, it's a miss, requiring retrieval from the database.

   Example: Requesting a new or less-used record.

4. **Cache Replacement Policy:** Rules for deciding which data to remove from the cache when it's full. Common policies include Least Recently Used (LRU) and First-In-First-Out (FIFO).

   Example: LRU policy removes the least recently accessed item from the cache.

5. **Cache Invalidation:** Removing or updating cached data when the database data changes to maintain consistency.

   Example: Deleting a record from the database removes it from the cache.

**Advantages of Caching:**

- **Improved Performance:** Faster access to frequently used data.
- **Reduced Database Load:** Less strain on the main database server.
- **Scalability:** Ability to handle more user requests without overloading the DBMS.

**Examples:**

1. **Web Page Caching:** Storing HTML pages, images, and often-used data to improve page load times and reduce server load.

2. **Query Result Caching:** Storing frequently executed query results, like product availability, for quick retrieval.

3. **Object Caching:** Storing objects or data from an Object-Relational Mapping (ORM) framework in memory to avoid repeated database access.

4. **API Response Caching:** Caching API responses to reduce requests to external services and improve application responsiveness.
