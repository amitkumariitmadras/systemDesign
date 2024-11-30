![image](https://github.com/user-attachments/assets/7a33587c-5d15-4e0e-a860-734d592c171e)

**TCP/IP Model Overview**  
The **TCP/IP** model, developed by the Department of Defense (DoD), is the foundation for communication on the internet. It consists of 5 layers, each responsible for different aspects of network communication.

---

### **1. Physical Layer**
- **Purpose**: Converts message bits into signals for transmission.
- **Medium**: Electrical signals for copper, light for fiber optics, and radio waves for wireless.
- **Characteristics**: Topology (bus, star, etc.), line configuration, transmission mode (simplex, duplex).

---

### **2. Data Link Layer (DLL)**
- **Sub-layers**:
  - **MAC (Media Access Control)**: Adds headers and trailers to data for addressing and error-checking.
  - **LLC (Logical Link Control)**: Handles flow control and error detection.
- **Functions**: Encapsulates IP packets into frames for transmission, ensures error detection and flow control.

---

### **3. Network Layer**
- **Purpose**: Adds logical addresses (IP addresses) and finds the best path for data delivery.
- **Protocols**:
  - **IP (Internet Protocol)**: Routes packets based on destination IP addresses; does not ensure delivery.
  - **ARP (Address Resolution Protocol)**: Maps IP addresses to MAC addresses.
  - **ICMP (Internet Control Message Protocol)**: Used for error reporting.

---

### **4. Transport Layer**
- **Purpose**: Manages flow control, end-to-end communication, and error-free data transmission.
- **Protocols**:
  - **TCP (Transmission Control Protocol)**: Connection-oriented, reliable, ensures correct data order and retransmits lost packets.
  - **UDP (User Datagram Protocol)**: Connectionless, faster, less reliable, no error checking.

---

### **5. Application Layer**
- **Purpose**: Provides network services to end users and applications.
- **Protocols**:
  - **HTTP (Hypertext Transfer Protocol)**: For accessing web pages.
  - **DNS (Domain Name System)**: Translates domain names to IP addresses.
  - **SMTP (Simple Mail Transfer Protocol)**: Used to send emails.
  - **FTP (File Transfer Protocol)**: Transfers files between computers.
  - **TELNET**: Provides remote access to machines.

--- 

This model helps ensure proper communication across the internet by organizing how data is handled from the physical transmission to the application layer.
