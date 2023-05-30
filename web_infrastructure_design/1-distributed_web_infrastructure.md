# <p align="center">Distributed Web Infrastructure</p>
<img src="" width="100%">

### Requirements

For this infrastructure, the requirements are as follows:

- 2 additional servers
- 1 web server (Nginx)
- 1 application server
- 1 load balancer (HAproxy)
- 1 set of application files (your code base)
- 1 database (MySQL)

### Description of the infrastructure
  
1. Servers

- We are adding two additional servers to improve the availability and processing capacity of the infrastructure. This distributes the workload and avoids a single point of failure.

2. Web server (Nginx)

- The Nginx web server is used to manage user requests and serve the static files of the website. It acts as a gateway between users and the application server.

3. Application server.

- The application server is responsible for executing the application code. It interprets the code and generates the dynamic web pages to be displayed to users.

4. Load splitter (HAproxy)

- The HAproxy load balancer is used to fairly distribute incoming requests between the different available servers. It improves the load distribution, availability and performance of the infrastructure.

4. Database (MySQL)

- The MySQL database is used to store and manage application data. It allows data persistence and allows application servers to access and manipulate the necessary information.

### Specificities of the infrastructure
  
- `Load splitter distribution algorithm`: The distribution algorithm used in HAproxy can be configured according to specific needs, such as round-robin, minimum number of connections, or IP-hash. This algorithm determines how requests are distributed among the available servers.

- `Load balancer configuration`: The load balancer is configured in active-passive mode. This means that only one server is active and processes incoming requests, while the other servers remain in passive mode and take over only in the event of an active server failure. This guarantees high availability of the website.

- `Primary-Replica database cluster`: The database cluster is configured using the Primary-Replica (Master-Slave) model. The primary node (master) manages write operations, while replicated nodes (slaves) manage read operations. The data is replicated asynchronously from the primary node to the replicated nodes to ensure data consistency and better availability.

- `Difference between the primary node and the replicated node`: The primary node is responsible for writing and updating the database. It is used by the application for write requests. The replicated nodes are used for read operations and serve as a backup in the event of a failure of the primary node. They guarantee high availability and improve performance by distributing read operations between replicated nodes.
  

### Potential infrastructure problems.
  
1. Single point of failure (SPOF):

- Each component of the infrastructure can become a single point of failure. In the event of a server, load balancer or database failure, this may lead to a service interruption or unavailability of the website.

2. Security issues:

- The current infrastructure does not include firewalls, which makes it vulnerable to attacks and intrusions. It is recommended to add a firewall to control network traffic and protect servers from potential threats.

- The absence of HTTPS (secure HTTP) exposes communications between users and the web server to the risk of data breach. The implementation of HTTPS is essential to secure exchanges and protect data confidentiality.

3. Lack of supervision:

- The infrastructure does not have a monitoring system in place. It is recommended to implement a monitoring system to monitor performance, detect problems and failures, and take preventive or corrective measures.