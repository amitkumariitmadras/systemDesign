### **What is Consistent Hashing?**

**Consistent hashing** is a technique used in distributed systems to map data (requests, objects) to servers, ensuring minimal disruption when servers are added or removed.

---

### **Key Concepts**

1. **Request Hashing**:
   - A **hash function** maps data to a **hash ring**.
   - Requests are routed to the **server** with the nearest hash value greater than or equal to the request's hash.

2. **Request Mapping**:
   - Servers are hashed and placed on the **ring**.
   - Requests are mapped to the closest server on the ring.

   **Example**:

   ```
   Hash Ring (0 to max):
     |----|----|----|----|----|
      0   25f3   53c4   67ab   b93c
               ^            ^
             Request       Server S2

   Servers:
     S1 -> 25f3
     S2 -> 67ab
     S3 -> b93c

   Request "client1" (Hash = 53c4) --> Routed to S2 (nearest server)
   ```

3. **Problems**:
   - **Imbalance** when servers are added/removed.
   - **High reshuffling** of data.

4. **Virtual Servers**:
   - Servers are mapped to multiple **virtual nodes** to balance data more evenly and reduce reshuffling.

   **Example**:  
   S1 → S1-1, S1-2, S1-3 (virtual nodes).

   ```
   Virtual Nodes Example:

   Hash Ring:
     |----|----|----|----|----|----|
      0   25f3   53c4   67ab   b93c   1000
                   ^               ^
                 Request           Virtual Node S1-2

   Servers:
     S1 -> 25f3, 25f4, 25f5 (virtual nodes)
     S2 -> 67ab
     S3 -> b93c
   ```

---

### **Applications**

1. **Distributed Caching**:  
   (e.g., **Memcached**, **Redis**) to distribute data across multiple nodes.

2. **Distributed Databases**:  
   (e.g., **Cassandra**, **DynamoDB**) for efficient data partitioning.

3. **CDNs**:  
   To route user requests to the closest server.

4. **Load Balancing**:  
   For balancing incoming traffic across servers.

---

### **Summary**
- **Consistent Hashing** efficiently distributes data, ensuring minimal disruption with server changes.
- Used in **caching**, **databases**, and **load balancing** systems.
- **Virtual nodes** improve data distribution and reduce reshuffling.
