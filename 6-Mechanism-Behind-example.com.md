### What Happens When You Type "example.com"?

When you type **example.com** in your browser and press Enter, several steps take place to load the website. Here's a breakdown:

---

### 1. **Check Browser Cache**
   - **Browser checks if the website was visited recently.**
   - If the IP address is cached, the website loads immediately.

### 2. **Operating System Lookup**
   - If the IP address is not cached, the browser asks the OS to find the IP address.
   - The OS first checks its **hosts file** for any mapped IP address.

### 3. **DNS Lookup**
   - If not found in the hosts file, the OS queries the **DNS Resolver** (usually provided by your ISP).
   - If the Resolver doesn’t have the IP address, it contacts the **Root DNS server**.
   - The Root server directs the request to the **TLD (Top-Level Domain) server** (e.g., for .com, the .COM TLD server).
   - The TLD server either has the IP cached or forwards the request to the **Authoritative Name Server** for example.com.
   - The Name Server returns the **IP address** for example.com.

### 4. **Send HTTP Request**
   - The OS sends a **GET request** to the obtained **IP address** for the website’s data.
   - The request is packaged using the **TCP** protocol and sent to the server.

### 5. **Firewall Check**
   - The request is checked by both the **OS** and the server's **firewalls** for any security issues.

### 6. **Server Response**
   - The server (often behind a **load balancer**) receives the request and sends back:
     - The **IP address** of the appropriate server.
     - An **SSL certificate** (if HTTPS, to ensure a secure connection).

### 7. **Send Website Data**
   - The server sends back the website’s files (HTML, CSS, JavaScript) to the OS.
   - The OS forwards these files to the browser for rendering.

### 8. **Render the Website**
   - The browser processes the HTML, CSS, and JavaScript files and displays **example.com**.

---

### Summary:
Although this process involves multiple steps, from DNS lookups to server communication, it all happens in **milliseconds**. This complexity is largely invisible to users but ensures seamless access to websites like **example.com**.
