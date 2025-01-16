# Web infrastructure design

**Dijeont Jean-Paul**

![Simple web Stack](./images/Diagramm_Tache0.png)


### **Key Points**

1. **Domain name**:  
   * `www.foobar.com` is configured with a **DNS A record** pointing to `8.8.8.8`.  
2. **Single server**:  
   * This server runs everything:  
     * **Nginx** (Web Server) on port 80 (HTTP) and 443 (HTTPS if SSL is configured).  
     * **Application Server** (the logic of your app, e.g., Node.js, Python/Flask, Gunicorn, etc.).  
     * **MySQL** (Database) on port 3306\.  
   * Your **code base** (HTML, CSS, JS, backend files, etc.) lives on the same machine.  
3. **Flow**:  
   * A user types `http://www.foobar.com` in a browser.  
   * DNS resolves `www.foobar.com` to `8.8.8.8`.  
   * The request reaches the single server.  
   * **Nginx** receives the request.  
     * If it’s a static file, Nginx can serve it directly.  
     * If it’s a dynamic request, Nginx forwards it to the **Application Server**, which processes the logic (queries database if needed).  
   * The application server connects to **MySQL** to read/write data.  
   * The response travels back through the application server → Nginx → user’s browser.

---

## **Explanation of Each Component**

1. **Server**  
   * A physical or virtual machine (IP: `8.8.8.8`) hosting all the software (Nginx, app server, MySQL).  
2. **Web Server (Nginx)**  
   * Receives incoming HTTP/HTTPS requests.  
   * Delivers static files (images, HTML, CSS).  
   * Passes dynamic requests to the application server.  
3. **Application Server**  
   * Runs your backend code (business logic).  
   * Communicates with the database to fetch or store data.  
4. **Database (MySQL)**  
   * Stores data in tables (e.g. users, products, posts).  
   * Listens on port 3306 by default.  
   * Responds to SQL queries from the application server.  
5. **Domain Name / DNS**  
   * `foobar.com` is your domain.  
   * A **www** record (type A) points `www.foobar.com` to `8.8.8.8`, letting users connect by typing `www.foobar.com` instead of an IP.  
6. **Communication Protocols**  
   * **HTTP** (port 80\) or **HTTPS** (port 443 if SSL is configured).  
   * The server uses TCP/IP behind the scenes to route data packets over the Internet.

---

## **Issues with This Infrastructure**

1. **Single Point of Failure (SPOF)**  
   1. If this one server goes down (hardware failure, crash, etc.), your entire website becomes inaccessible.  
2. **Downtime During Maintenance**  
   1. When you deploy new code or reboot the server (e.g., for updates), the site can be offline.  
   2. You have no redundancy.  
3. **Scaling Limitations**  
   1. If traffic grows significantly, this single server might not handle all the requests.  
   2. There’s no load balancer or additional servers to distribute the load.
