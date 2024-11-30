### **Scaling Writes in Databases: The Power of the Log**

To efficiently handle heavy write workloads, **Log-Structured Merge Trees (LSM Trees)** are used instead of traditional **B+ Trees**, which are slower under high write pressure. Here’s how they work:

---

### **Key Concepts**:

1. **Log-based Request Condensing**:
   - Writes are **appended to a log** instead of modifying data structures directly, reducing disk operations.
   
   **Visualization**:
   ```
   Log: Request1 -> Request2 -> Request3
   ```

2. **Log using Linked List**:
   - Data is stored in a **linked list** of logs, where each entry points to the next, avoiding rebalancing overhead.

   **Visualization**:
   ```
   Log: Entry1 -> Entry2 -> Entry3
   ```

3. **B-plus Tree vs Linked List**:
   - **B+ Trees** require rebalancing on each write, which is inefficient under heavy load.
   - **Log-structured approach** (Linked List) avoids this, appending new data efficiently.

4. **Sorted String Table (SSTable)**:
   - Writes are stored in logs, then periodically merged into **sorted SSTables** for fast lookups.
   
   **Visualization**:
   ```
   Log -> MemTable -> SSTable (Sorted)
   ```

5. **Compaction**:
   - Merging smaller SSTables into larger ones removes duplicates and frees up space.
   
   **Visualization**:
   ```
   [SSTable1] + [SSTable2] -> [Compacted SSTable]
   ```

6. **Bloom Filters**:
   - **Bloom Filters** quickly check if a key exists in an SSTable before performing an expensive search.
   
   **Visualization**:
   ```
   Key → Bloom Filter → (Check if the key exists)
   ```

---

### **Summary**:

- **LSM Trees** use a log-based structure to efficiently handle writes without frequent rebalancing, storing data in **SSTables**.
- **Compaction** optimizes storage, and **Bloom Filters** speed up reads by minimizing unnecessary disk I/O.
