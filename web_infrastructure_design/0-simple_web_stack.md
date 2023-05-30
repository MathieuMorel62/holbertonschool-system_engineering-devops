# <p align="center">Web Infrastructure Design</p>
<img src="https://github.com/MathieuMorel62/holbertonschool-system_engineering-devops/assets/113856302/b9fd47aa-3ad2-4cde-b9ef-a4ca99bf41e2" width="100%">

### Server

A server is a computer that provides data and services to other computers over a network. In this context, it hosts our web server (Nginx), application server, application files (our codebase), and a database (MySQL). It accepts requests, processes these according to defined business logic, and returns an appropriate response.

### Domain Name

The domain name serves as a human-friendly address of a website. Instead of typing an IP address, users can type a domain name like www.foobar.com. The DNS system will then translate this domain name into an IP address that points to the server where the website is hosted.

### DNS Record

The `www` in www.foobar.com is a type of DNS record called a CNAME (Canonical Name). This record maps the domain name to another domain. In this case, it is typically used to ensure that both the domain and the `www` subdomain lead to the same application on the server.

### Web Server (Nginx)

A web server serves as an intermediary between the client (usually a web browser) and the application server. It accepts HTTP requests from the client, forwards them to the application server for processing, and then sends the response back to the client. It also handles the delivery of static content, SSL termination, and other tasks related to serving web content.

### Application Server

The application server runs the business logic of the web application. It processes requests received from the web server, interacts with the database to store or retrieve data, and compiles the application files into HTML content that can be served to the client.

### Database (MySQL)

The database is where all data necessary for the application is persistently stored. This can include user information, application data, and other types of data. The application server queries the database to retrieve the necessary data for generating dynamic web content.

### Server-User Communication

The server uses the Hypertext Transfer Protocol (HTTP) to communicate with the user's computer requesting the website. The user's web browser sends an HTTP request to the server, which then sends an HTTP response back to the user's browser.

## Potential Issues with this Infrastructure

- **Single Point of Failure (SPOF)**: As everything is hosted on a single server, if that server goes down for any reason, the entire application will be unavailable.

- **Downtime during Maintenance** : If you need to update the application code or restart the web server, the application will be unavailable during this time. This can result in a poor user experience.

- **Unable to Handle Increased Traffic** : With everything running on a single server, there's a limit to how much traffic it can handle. If the application experiences a significant increase in usage, the server might struggle to handle all the traffic, resulting in slowdowns or even outages.
