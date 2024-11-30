### **Introduction to NoSQL Databases**
- **NoSQL** databases are **non-relational** and designed to store **unstructured** or **semi-structured** data.
- They provide **horizontal scalability**, making them ideal for high-volume, large-scale applications.

---

### **Types of NoSQL Databases and Examples**

#### 1. **Document-based (e.g., MongoDB)**  
- **Data Storage**: Uses **JSON-like documents**.
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

#### 2. **Key-Value Store (e.g., Redis)**  
- **Data Storage**: Stores data as **key-value pairs**.
- **Real-life Example**: **Session data** for logged-in users.
- **Example Key-Value Pair**:
  ```
  Key: "session:12345"
  Value: {"user": "john_doe", "cart": ["item1", "item2"]}
  ```

#### 3. **Column-family Store (e.g., Cassandra)**  
- **Data Storage**: Stores data in **columns** instead of rows.
- **Real-life Example**: **User activity logs** or **time-series data**.
- **Example Table (User Activity Logs)**:
  | Timestamp          | User ID | Action    | Status  |
  |--------------------|---------|-----------|---------|
  | 2023-11-01 10:00   | 001     | Login     | Success |
  | 2023-11-01 10:05   | 002     | Purchase  | Success |

#### 4. **Graph Database (e.g., Neo4j)**  
- **Data Storage**: Stores data as **graphs** with **nodes (entities)** and **edges (relationships)**.
- **Real-life Example**: **Social media connections** (friends, followers).
- **Example Graph**:  
  - **Nodes**: `John`, `Alice`, `Bob`
  - **Edges**: `John -> Alice (Friend)`, `Alice -> Bob (Follows)`

---

### **Key Cassandra Concepts with Examples**

#### **1. Cassandra Architecture**
- **Decentralized**: No single point of failure, all nodes are **equal**.
- **Real-life Example**: A **video streaming platform** using Cassandra to store user activity logs for high availability.
  
  **Example Table (User Activity Logs)**:
  | Timestamp          | User ID | Action    | Status  |
  |--------------------|---------|-----------|---------|
  | 2023-11-01 10:00   | 001     | Play      | Success |
  | 2023-11-01 10:05   | 002     | Pause     | Success |
  | 2023-11-01 10:10   | 003     | Stop      | Failed  |

---

#### **2. Quorum in Cassandra**
- **Definition**: **Quorum** requires a majority of nodes (e.g., 3 out of 5) to agree on a read/write operation to maintain **data consistency**.
- **Real-life Example**: A **banking system** ensures transactions are confirmed by a majority of nodes before processing.

  **Example Use Case**:  
  For a write operation in a 5-node cluster, at least 3 nodes must acknowledge the write before it’s considered successful.

---

#### **3. Compaction of SSTables**
- **SSTables**: Data is stored in **Sorted String Tables (SSTables)**. Over time, smaller SSTables are merged (compacted) into larger ones.
- **Compaction**: Improves **storage efficiency** and **query performance** by removing duplicates and reducing free space.

  **Example Table (Product Inventory)**:
  | Timestamp          | Product ID | Action   | Quantity |
  |--------------------|------------|----------|----------|
  | 2023-11-01 09:00   | P001       | Added    | 10       |
  | 2023-11-01 10:00   | P002       | Sold     | 5        |
  | 2023-11-01 11:00   | P001       | Sold     | 3        |

  After compaction, old SSTables merge, optimizing storage and speeding up queries.

---

### **Summary**
- **NoSQL Databases**: Non-relational, ideal for **large-scale**, **high-volume** applications needing **horizontal scalability**.
- **Cassandra**:
  - **Decentralized** and **highly available** architecture.
  - **Quorum** ensures consistency by requiring a majority of nodes to agree on operations.
  - **Compaction** optimizes storage and query performance by merging smaller SSTables.

- **Example Scenarios**:  
  - **Document-based (MongoDB)**: Storing flexible data like user orders.
  - **Key-Value (Redis)**: Managing user session data.
  - **Column-family (Cassandra)**: Storing time-series or logs (e.g., user activity).
  - **Graph (Neo4j)**: Representing relationships in social networks.

These NoSQL databases are designed for **real-time**, **big-data** applications in areas like **social networks**, **e-commerce**, **video streaming**, and more.
