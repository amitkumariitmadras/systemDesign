### **Difference Between Program, Process, and Thread**

---

### **1. Program**
- **Definition**: A program is a passive set of instructions stored as an executable file (e.g., `.exe`, `.bin`).
- **Characteristics**:
  - Stored in **secondary storage** (disk).
  - **No resource usage** until executed.
  - **Indefinite lifespan**.

**Example**:  
A Python script (`hello_world.py`) on your disk is a **program**. It’s just a file with instructions, and it isn't using CPU or memory until you run it.

---

### **2. Process**
- **Definition**: A process is an active instance of a program in execution.
- **Characteristics**:
  - Resides in **main memory** (RAM).
  - **Requires resources** like CPU, memory, and I/O.
  - **Finite lifespan**.
  - Includes **stack**, **heap**, and **data section**.

**Example**:  
When you run the Python script (`python hello_world.py`), it becomes a **process**. The program is loaded into memory and the system allocates CPU time and resources for execution.

---

### **3. Thread**
- **Definition**: A thread is the smallest unit of execution within a process.
- **Characteristics**:
  - Shares **resources** (code, data) of its process.
  - Owns its **program counter** and **stack**.
  - **Lightweight** and **quick to create/terminate**.

**Example**:  
If you modify the Python script to use **multithreading** (e.g., downloading data while processing), each of these tasks is handled by a **thread**. Threads share the same process but can run independently.

---

### **Key Differences**

| **Aspect**            | **Program**                  | **Process**                     | **Thread**                      |
|-----------------------|------------------------------|---------------------------------|---------------------------------|
| **Entity**            | Passive                      | Active                          | Smallest unit of execution     |
| **Storage**           | Stored in disk               | Loaded into memory (RAM)        | Part of a process in memory    |
| **Resource Use**      | No resources used            | Requires CPU, memory, I/O       | Shares resources with process  |
| **Lifespan**          | Indefinite                   | Finite                          | Lives as long as process runs |
| **Context Switching** | N/A                          | Slower                          | Faster and lighter             |
| **Creation/Termination** | N/A                        | More complex                    | Easier and faster              |

---

### **Types of Processes**

1. **I/O Bound Process**  
   - Spends more time doing I/O operations (e.g., waiting for data from disk or network).
   
   **Example**: A program that frequently reads data from a disk or waits for network responses.

2. **CPU Bound Process**  
   - Spends more time performing CPU-intensive computations.

   **Example**: A program that performs complex calculations or data processing without much I/O.

---

### **Summary**
- **Program**: A file with instructions (e.g., `hello_world.py`).
- **Process**: A running instance of a program (e.g., `python hello_world.py`).
- **Thread**: A lightweight unit of execution within a process (e.g., downloading and processing data in parallel using threads).
