# What Happens When You Type google.com in Your Browser and Press Enter

## **Overview**

This project explores the intricate process that occurs when you type `https://www.google.com` in your browser and press Enter. It breaks down the flow of the request through various layers of the web stack, showcasing essential concepts like DNS resolution, encryption, firewalls, load balancing, server interactions, and database communication.

This README provides a comprehensive explanation of the tasks completed, including a schema illustrating the request flow and detailed steps involved.

---

## **Tasks and Requirements**

### **Task 0: What Happens When...**

In this task, I wrote a blog post explaining the journey of a web request from the browser to the database and back. The post covers the following elements:

1. **DNS Request**
   - Resolving `www.google.com` into an IP address through DNS queries.

2. **TCP/IP**
   - Establishing a reliable connection between the client and the server via a three-way handshake.

3. **Firewall**
   - Filtering the request to ensure security.

4. **HTTPS/SSL**
   - Encrypting the communication between the browser and the server using a TLS handshake.

5. **Load Balancer**
   - Distributing the request to one of the available servers.

6. **Web Server**
   - Handling static files and forwarding dynamic requests to the application server.

7. **Application Server**
   - Processing business logic and querying the database if necessary.

8. **Database**
   - Retrieving the required data and sending it back to the application server.

---

### **Task 1: Everything's Better with a Pretty Diagram**

I created a schema to visually represent the flow of a web request. The diagram includes:

- DNS resolution.
- Connection to the server using the appropriate port.
- Encrypted traffic via HTTPS/TLS.
- Firewall filtering.
- Request distribution through a load balancer.
- Response generation by the web and application servers.
- Database interaction for retrieving data.

#### **Diagram**

![Web Request Flow Diagram](./images/blog_post.png)

---

## **Explanation of the Process**

### **1. DNS Resolution** 🌍
   - The browser sends a DNS request to resolve `www.google.com` into an IP address by querying DNS caches and servers.

### **2. TCP/IP Connection** 🔗
   - Establishes a reliable connection using a three-way handshake (SYN, SYN-ACK, ACK).

### **3. Firewall** 🔒
   - Filters the traffic to block malicious or unauthorized requests.

### **4. HTTPS/SSL Encryption** 🔐
   - Encrypts the communication via a TLS handshake to ensure secure data transfer.

### **5. Load Balancer** ⚖️
   - Distributes incoming requests across multiple servers for efficient load handling.

### **6. Web Server** 🌐
   - Serves static content like HTML, CSS, and JavaScript. Forwards dynamic requests to the application server.

### **7. Application Server** 🛠️
   - Executes business logic and queries the database if needed.

### **8. Database** 📊
   - Retrieves the requested data and returns it to the application server for response generation.

### **9. Response Delivery** 🚀
   - The response is sent back through the load balancer to the browser, where the page is rendered.

---

## **Tools Used**

- **Diagram.io (Draw.io)**: Used to create a professional and clear visual representation of the request flow.
- **Markdown**: For writing structured and readable documentation.

---

## **Conclusion**

This project highlights the complexity and efficiency of modern web infrastructure. Understanding the journey of a web request enhances knowledge of essential networking, server, and database concepts, making it a valuable exercise for software engineers and tech enthusiasts alike.

The blog post and diagram illustrate these concepts clearly, fulfilling the project requirements and providing a comprehensive view of the process.

## Author
**Jean-Paul Dijeont**