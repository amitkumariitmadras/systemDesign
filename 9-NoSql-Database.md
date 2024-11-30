### **Introduction to NoSQL Databases**

NoSQL databases are **non-relational** and are used to store **unstructured or semi-structured data**. They are designed to scale easily across many servers.

---

### **Types of NoSQL Databases and Examples**

1. **Document-based (e.g., MongoDB)**  
   - Stores data in **JSON-like documents**.
   - **Real-life Example**: E-commerce site storing **user orders**.
   - **Example Document**:
     ```json
     {
       "_id": "12345",
       "user": "john_doe",
       "order": [
         {"item": "Laptop", "price": 1000},
         {"item": "Mouse", "price": 25}
       ],
       "total": 1025
     }
     ```

2. **Key-Value Store (e.g., Redis)**  
   - Stores data as **key-value pairs**.
   - **Real-life Example**: Session data for logged-in users.
   - **Example Key-Value Pair**:
     ```
     Key: "session:12345"
     Value: {"user": "john_doe", "cart": ["item1", "item2"]}
     ```

3. **Column-family Store (e.g., Cassandra)**  
   - Stores data in **columns** rather than rows.
   - **Real-life Example**: Storing time-series data, like **user activity logs**.
   - **Example Table**:
     | Timestamp          | User ID | Action    | Status |
     |--------------------|---------|-----------|--------|
     | 2023-11-01 10:00   | 001     | Login     | Success|
     | 2023-11-01 10:05   | 002     | Purchase  | Success|

4. **Graph Database (e.g., Neo4j)**  
   - Stores data as **graphs** with **nodes (entities)** and **edges (relationships)**.
   - **Real-life Example**: Social media connections (friends, followers).
   - **Example Graph**:  
     - **Nodes**: `John`, `Alice`, `Bob`
     - **Edges**: `John -> Alice (Friend)`, `Alice -> Bob (Follows)`

---

### **Summary**
- **Document-based**: Stores flexible data (e.g., user orders in JSON).
- **Key-Value**: Stores simple pairs (e.g., user session info).
- **Column-family**: Stores data by columns (e.g., logs, time-series).
- **Graph**: Stores relationships between entities (e.g., social network connections).

These databases are highly scalable and used in real-time, big-data applications like social networks, e-commerce, and more.
