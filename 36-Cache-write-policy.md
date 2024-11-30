### **Cache Consistency Policies**

1. **Write-through Cache**  
   - **How it Works**: Data is written to both the cache and the database simultaneously.  
   - **Pros**: Ensures data consistency between cache and database.  
   - **Cons**: Slower writes, as both systems must be updated at the same time.  

2. **Write-back Cache**  
   - **How it Works**: Data is written to the cache first, and updates are later pushed to the database.  
   - **Pros**: Reduces database load, faster write operations.  
   - **Cons**: Potential for temporary data inconsistency between the cache and database.

3. **Read-through Cache**  
   - **How it Works**: If data is not found in the cache, it is fetched from the database and stored in the cache.  
   - **Pros**: Transparent to the application, ensuring cache is always populated when needed.  
   - **Cons**: Slight overhead on initial cache misses.

4. **Cache Eviction Policies**  
   - **Least Recently Used (LRU)**: Evicts the least recently used items first.  
   - **First In First Out (FIFO)**: Evicts the oldest items in the cache.  
   - **Least Frequently Used (LFU)**: Evicts the least frequently accessed items.

---

### **Visuals:**

**Write-through vs Write-back Cache**
```
Write-through:       [Cache] ⇄ [DB]  
Write-back:          [Cache] → [DB (Delayed)]
```

**Cache Eviction Example:**
```
LRU Eviction:       [Item1] [Item2] [Item3] -> Evict Item1
FIFO Eviction:      [Item1] [Item2] [Item3] -> Evict Item1
LFU Eviction:       [Item1 (5 hits)] [Item2 (2 hits)] [Item3 (1 hit)] -> Evict Item3
```

These policies ensure that data is managed effectively in distributed systems to balance speed, consistency, and memory usage.
