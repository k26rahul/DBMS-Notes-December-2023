**Candidate Keys:**
A candidate key is a minimal set of attributes in a relational table that uniquely identifies each row, with no redundant attributes. Removing any attribute from it would result in non-uniqueness.

**Super Keys:**
A super key is a set of attributes that can uniquely identify rows but may contain more attributes than necessary to ensure uniqueness.

**Example:**
In a music library's "Songs" table:

**Songs Table:**

| SongID | Title              | Artist     | Album             | Genre    | Year |
|--------|--------------------|------------|-------------------|----------|------|
| 1      | "Bohemian Rhapsody" | Queen    | "A Night at the Opera" | Rock     | 1975 |
| 2      | "Imagine"          | John Lennon | "Imagine"        | Rock     | 1971 |
| 3      | "Shape of You"     | Ed Sheeran  | "÷ (Divide)"      | Pop      | 2017 |
| 4      | "Rolling in the Deep" | Adele | "21"               | Pop      | 2010 |

**Candidate Key:**
- The "SongID" is a candidate key for uniquely identifying songs, and it is both minimal and unique.

**Super Key:**
- A super key for the "Songs" table could be the combination of "Title" and "Year." Although unique, it's not minimal because a song can be identified using just the "SongID."