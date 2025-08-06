**Apache Tomcat 5.x / 6.x**

**1. What is Apache Tomcat?**

**Answer:** Tomcat is an open-source implementation of Java Servlet,
JavaServer Pages, and Java Expression Language technologies. It acts as
a web container that runs Java web applications.

**2. How does Tomcat handle requests?**

**Answer:** When a request comes in, Tomcat uses its Connector component
to pass the request to a ServletContainer, which then maps the request
to a servlet or JSP for processing.

**3. What are the main configuration files in Tomcat?**

**Answer:**

- server.xml -- Core server configuration

- web.xml -- Default web application deployment descriptor

- context.xml -- Per-application context configuration

**4. What is the difference between Tomcat 5.x and 6.x?**

**Answer:**

- Tomcat 6.x supports Servlet 2.5 and JSP 2.1.

- Tomcat 5.x supports Servlet 2.4 and JSP 2.0.

- Tomcat 6.x introduced improvements in performance and class loading.

**Nginx 1.18**

**1. What is Nginx used for?**

**Answer:** Nginx is a high-performance HTTP server, reverse proxy, and
load balancer. It is also used to serve static content efficiently.

**2. How is Nginx different from Apache HTTP Server?**

**Answer:**

- Nginx uses an event-driven, asynchronous architecture, making it more
  scalable under load.

- Apache uses a process/thread-based model.

- Nginx is better suited for static content and reverse proxy scenarios.

**3. How do you configure reverse proxy in Nginx?**

**Answer:**

nginx

CopyEdit

server {

listen 80;

location / {

proxy_pass http://localhost:8080;

}

}

**4. How does Nginx handle high concurrency?**

**Answer:** Nginx uses an event loop model (epoll/kqueue) where a single
thread can handle thousands of connections asynchronously.

**IBM Liberty Profile**

**1. What is IBM Liberty?**

**Answer:** Liberty is a lightweight, fast, and modular Java EE
application server provided by IBM. It is part of WebSphere family.

**2. What are Liberty server features?**

**Answer:** Liberty uses a feature-based model. You enable only what
your application needs (e.g., servlet-4.0, jpa-2.2, jaxrs-2.0).

**3. How is Liberty different from traditional WAS?**

**Answer:**

- Liberty is lightweight and modular.

- Faster startup time.

- Easier to configure (XML/YAML).

- Ideal for microservices and container environments.

**4. Where is the server configuration stored?**

**Answer:** In server.xml located in the Liberty server directory under
wlp/usr/servers/\<server_name\>/.

**WebSphere Application Server 9 (WAS9)**

**1. What is WAS9 used for?**

**Answer:** WAS9 is an enterprise-level application server for deploying
and managing Java EE applications. It provides scalability, reliability,
and robust integration with IBM tools.

**2. What is the difference between Base, ND, and Liberty in WAS?**

**Answer:**

- **Base:** Standalone server profile

- **ND (Network Deployment):** Supports clustering, load balancing, and
  distributed deployment

- **Liberty:** Lightweight, cloud-friendly version

**3. What are cells, nodes, and servers in WAS?**

**Answer:**

- **Cell:** Logical grouping of nodes and servers

- **Node:** Logical grouping of application servers managed by a node
  agent

- **Server:** Runtime instance of an application

**4. What is Deployment Manager (DMGR)?**

**Answer:** DMGR is a central administration tool in WAS ND for managing
multiple nodes and servers in a cell.

**5. How is clustering handled in WAS9?**

**Answer:** WAS9 supports workload management using clusters.
Applications deployed to a cluster can run on multiple JVMs, providing
high availability.
