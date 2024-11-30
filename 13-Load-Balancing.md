### **What is Load Balancing?**

**Load balancing** distributes incoming network traffic across multiple servers to prevent any single server from becoming overwhelmed, improving performance and scalability.

---

### **Key Points**

1. **Goal**:  
   - Distribute traffic evenly.  
   - Prevent server overload.  
   - Improve availability and fault tolerance.

2. **How it Works**:  
   - A **load balancer** routes client requests to the least loaded server.

---

### **Example**:
- A website with 3 servers (S1, S2, S3). The load balancer distributes incoming requests evenly across these servers.

---

### **Key Terms: Server-Client**  
- **Server**: Provides resources (e.g., web or database server).  
- **Client**: Requests services (e.g., browser or app).

---

### **Scaling**:  
- **Vertical Scaling**: Add more power to a single server.  
- **Horizontal Scaling**: Add more servers (commonly used with load balancing).

---

### **Hashing Requests**:  
- **Consistent Hashing**: A method for mapping requests to servers using a hash function. It minimizes disruptions when servers are added or removed.

---

### **Visualizing Hashing Requests**:
Imagine you have 3 servers, and we use a **hash function** to route requests:

1. **Clients** send requests.
2. A **hash function** assigns each request to a specific server based on a calculated hash value.

```
Client Request --> Hash Function --> Route to Server

        Hash Ring:
    |----|----|----|----|----|
     S1   S2   S3   S4   S5
    |----|----|----|----|----|
 
    Request 1 --> Hash: S3
    Request 2 --> Hash: S1
    Request 3 --> Hash: S2
    Request 4 --> Hash: S3
    ...
```

```
Hash Ring (0 to max value):
   |----|----|----|----|----|----|----|
    0   25f3   53c4   67ab   b93c   Max

Server Hashes:
  S1: 25f3
  S2: 67ab
  S3: b93c

Request Hash:
  client1 --> 53c4 --> assigned to S2
```

- **Requests are routed** to servers (S1, S2, S3) based on their hashed value.
- **Consistency**: If a server is added or removed, only a small portion of requests are rerouted.

---

### **Request Stickiness**:  
- Ensures a client’s requests go to the same server throughout a session (important for maintaining session state, like login or shopping cart).

---

### **Summary**:  
- **Load balancing** distributes traffic across servers for **scalability** and **fault tolerance**.  
- **Consistent hashing** ensures efficient request routing with minimal disruption when servers change.
