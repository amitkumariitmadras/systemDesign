### **Transaction Isolation Levels**

In relational databases, **transaction isolation levels** define how the changes made by one transaction are visible to others. These levels control **concurrency** and **data consistency**.

---

### **Isolation Levels**

1. **Read Uncommitted**:
   - Allows **dirty reads**: A transaction can read uncommitted changes from another transaction.
   - **Low isolation** and **high performance** but may lead to inconsistent data.
   - Example: A transaction reads data that may later be rolled back.

2. **Read Committed**:
   - Prevents **dirty reads**: A transaction only reads data that has been committed.
   - **Medium isolation**: Still allows **non-repeatable reads** (data may change between reads within a transaction).
   - Example: Two transactions reading the same data may get different results if one updates it.

3. **Repeatable Read**:
   - Prevents **dirty reads** and **non-repeatable reads**.
   - Ensures that once data is read in a transaction, it cannot change during that transaction.
   - **Higher isolation**: Still allows **phantom reads** (new rows might be inserted or deleted).
   - Example: A transaction consistently reads the same data, but new data could appear.

4. **Serializable**:
   - Provides **the highest level of isolation**.
   - Ensures that transactions behave as if they were executed serially, one after another.
   - **Prevents dirty reads**, non-repeatable reads, and phantom reads.
   - Example: Transactions are fully isolated, ensuring no overlap or conflicting changes.

---

### **Trade-offs in Performance and Consistency**

| **Isolation Level**  | **Dirty Reads**   | **Non-repeatable Reads** | **Phantom Reads**  | **Performance Impact** |
|----------------------|-------------------|--------------------------|--------------------|------------------------|
| **Read Uncommitted**  | Allowed           | Allowed                  | Allowed            | Low                    |
| **Read Committed**    | Not Allowed       | Allowed                  | Allowed            | Medium                 |
| **Repeatable Read**   | Not Allowed       | Not Allowed              | Allowed            | High                   |
| **Serializable**      | Not Allowed       | Not Allowed              | Not Allowed        | Very High              |

---

### **Visual Representation**

1. **Read Uncommitted**:  
   - Transaction 1 writes, Transaction 2 reads dirty data.

   ```
   T1: Write X = 100
   T2: Read X = 100 (dirty read)
   ```

2. **Read Committed**:  
   - Transaction 1 commits, then Transaction 2 reads committed data.

   ```
   T1: Write X = 100 (committed)
   T2: Read X = 100 (committed)
   ```

3. **Repeatable Read**:  
   - Transaction 1 reads data and prevents changes during its lifetime.

   ```
   T1: Read X = 100
   T2: Write X = 200 (T1 still sees X = 100)
   ```

4. **Serializable**:  
   - Ensures all transactions are serially executed.

   ```
   T1: Read X = 100, Write X = 150
   T2: Read X = 100 (waiting for T1 to commit)
   ```

---

### **Summary**

- **Read Uncommitted**: Allows the least isolation, higher risk of inconsistencies.
- **Read Committed**: Avoids dirty reads, but still allows non-repeatable reads.
- **Repeatable Read**: Prevents non-repeatable reads but may face phantom reads.
- **Serializable**: Guarantees the highest isolation, ensuring serial transaction execution, but impacts performance. 

Choosing the appropriate isolation level depends on balancing **data consistency** with **system performance**.
