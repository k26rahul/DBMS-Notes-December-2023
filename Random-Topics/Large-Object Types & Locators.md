- Large-Object Types & Locators
  - Manage large data (e.g., images, videos)
  - Store reference (locator) in database
  - Actual data stored externally
  - Improved performance, less space
  - DBMS-specific: BLOBs, CLOBs
  - Supports streaming, retrieval
  - Use when data exceeds regular storage
  - Locator points to data location

**BLOB (Binary Large Object):** Stores binary data (e.g., images).

- 👉 Storing user profile pictures in a social media database.

**CLOB (Character Large Object):** Stores character/text data (e.g., documents).

- 👉 Storing articles, essays, or legal documents in a content management system.

**BFILE (Binary File):** Stores binary data as pointers to external files.

- 👉 Managing large video files outside the database while tracking their locations.

**Locators**

- Pointers or references to large-object data stored outside the database.
- Store data location, not data itself
- Efficiently manage large objects
- Minimize storage overhead
- Improve data retrieval performance
- Used for large files, multimedia data
- Database-specific implementation
- They're used to manage large data efficiently, like BFILE.
- Example: Using BFILE locators to track and access large video files stored externally for a video-sharing platform.
