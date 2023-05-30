# <p align="center">Web Infrastructure Design</p>
<img src="https://github.com/MathieuMorel62/holbertonschool-system_engineering-devops/assets/113856302/b9fd47aa-3ad2-4cde-b9ef-a4ca99bf41e2" width="100%">

### Server

A server is a computer that provides data and services to other computers over a network. It is typically located in a data center and can be either physical or virtual. The server runs on an operating system, which is the software that executes programs and manages hardware resources.

In this context, our server hosts a web server (Nginx), an application server, application files (our codebase), and a database (MySQL). It accepts requests, processes them according to a defined business logic, and returns an appropriate response.

### Domain Name and DNS Record

- The domain name serves as a user-friendly address for a website. Instead of typing in an IP address, users can type in a domain name like www.foobar.com. The DNS system then translates this domain name into an IP address that points to the server where the website is hosted.

- `www` in www.foobar.com is a type of DNS record called CNAME (Canonical Name). This record maps the domain name to another domain. In this case, it is generally used to ensure that the domain and subdomain `www` go to the same application on the server.

### Web Server (Nginx)

The role of a web server is to serve web pages or static content. In our case, Nginx acts as an intermediary between the client (usually a web browser) and the application server. It accepts HTTP requests from the client, forwards them to the application server for processing, and then sends the response back to the client.

### Application Server

The application server executes the business logic of the web application, which allows it to produce dynamic content. It processes requests received from the web server, interacts with the database to store or retrieve data, and compiles the application files into HTML content that can be served to the client.

### Database (MySQL)

The database is where all the data necessary for the application is persistently stored. This can include user information, application data, and other types of data. The application server queries the database to retrieve the necessary data for generating dynamic web content.

### Server-User Communication

The server uses the Hypertext Transfer Protocol (HTTP) to communicate with the user's computer requesting the website. The user's web browser sends an HTTP request to the server, which then sends an HTTP response back to the user's browser. This communication happens over a network using the TCP/IP protocol.

## Potential Issues with this Infrastructure

- **Single Point of Failure (SPOF)**: As everything is hosted on a single server, if that server fails for any reason, the entire application will be unavailable. This is a single point of failure as there is no redundancy in this setup.

- **Downtime during Maintenance**: If you need to update the application code or restart the web server, the application will be unavailable during that time. This can lead to a poor user experience.

- **Unable to Handle Increased Traffic**: With everything running on a single server, there's a limit to how much traffic it can handle. If the application sees a significant increase in usage, the server might struggle to handle all the traffic, resulting in slowdowns or even outages. This means that this infrastructure cannot scale and will not be able to handle traffic that would exceed the server's capacity.
