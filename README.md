# <p align="center">Web infrastructure design</p>
<img src="https://370ztech.com/wp-content/uploads/2020/06/Understanding-Network-Infrastructure-Design.jpg" width="100%">

## Introduction

As part of this project, we will focus on designing a web infrastructure from scratch. We will examine the key concepts of infrastructure design, including network bases, servers, web servers, DNS, load balancers and monitoring.

## Resources
### Read or Watch:

- [Network Basics Concept Page](https://intranet.hbtn.io/concepts/791)
- [Server Concept Page](https://intranet.hbtn.io/concepts/799)
- [Web Server Concept Page](https://intranet.hbtn.io/concepts/800)
- [DNS Concept Page](https://intranet.hbtn.io/concepts/803)
- [Load Balancer Concept Page](https://intranet.hbtn.io/concepts/804)
- [Monitoring Concept Page](https://intranet.hbtn.io/concepts/805)
- [What Is a Database](https://www.techtarget.com/searchdatamanagement/definition/database)
- [What’s The Difference Between a Web Server And An App Server?](https://www.youtube.com/watch?v=S97eKyv2b9M)
- [DNS Record Types](https://ns1.com/resources/dns-types-records-servers-and-queries)
- [Single Point Of Failure](https://en.wikipedia.org/wiki/Single_point_of_failure)
- [How To Avoid Downtime When Deploying New Code](https://softwareengineering.stackexchange.com/questions/35063/how-do-you-update-your-production-codebase-database-schema-without-causing-downt#answers-header)
- [High Availability Cluster (active-active/active-passive)](https://docs.oracle.com/cd/E17904_01/core.1111/e10106/intro.htm#ASHIA712)
- [What Is HTTPS](https://www.instantssl.com/http-vs-https)
- [What Is a Firewall](https://www.webopedia.com/definitions/firewall/)

## Description of the project

The purpose of this project is to design and explain a fully functional web infrastructure. To do this, we will start from the explanation of a simple web server and evolve to a distributed, secure and monitored infrastructure capable of managing traffic and resizing itself as needed.
  
The learning objectives of this project include the ability to draw a diagram representing the web infrastructure you built during the projects on the sysadmin/devops track, to explain what each component does, and to explain the redundancy of the system.

## Conclusion

This project is designed to help you understand the ins and outs of designing a web infrastructure. This is an essential aspect of any role as a DevOps engineer and this experience will help you be better prepared for these challenges.

-----------------------

## Tasks

### [0. Simple Web Stack](https://github.com/MathieuMorel62/holbertonschool-system_engineering-devops/blob/main/web_infrastructure_design/0-simple_web_stack.md)

A lot of websites are powered by simple web infrastructure, a lot of time it is composed of a single server with a [LAMP stack](https://en.wikipedia.org/wiki/LAMP_%28software_bundle%29).
  
On a whiteboard, design a one server web infrastructure that hosts the website that is reachable via `www.foobar.com`. Start your explanation by having a user wanting to access your website.
  
**Requirements:**

- You must use:
  - 1 server
  - 1 web server (Nginx)
  - 1 application server
  - 1 application files (your code base)
  - 1 database (MySQL)
  - 1 domain name `foobar.com` configured with a `www` record that points to your server IP `8.8.8.8`

- You must be able to explain some specifics about this infrastructure:
  - What is a server
  - What is the role of the domain name
  - What type of DNS record `www` is in `www.foobar.com`
  - What is the role of the web server
  - What is the role of the application server
  - What is the role of the database
  - What is the server using to communicate with the computer of the user requesting the website
  
- You must be able to explain what the issues are with this infrastructure:
  - SPOF
  - Downtime when maintenance needed (like deploying new code web server needs to be restarted)
  - Cannot scale if too much incoming traffic

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-------------------

### [1. Distributed Web Infrastructure](https://github.com/MathieuMorel62/holbertonschool-system_engineering-devops/blob/main/web_infrastructure_design/1-distributed_web_infrastructure.md)

On a whiteboard, design a three server web infrastructure that hosts the website `www.foobar.com`.
  
**Requirements:**

- You must add:
  - 2 servers
  - 1 web server (Nginx)
  - 1 application server
  - 1 load-balancer (HAproxy)
  - 1 set of application files (your code base)
  - 1 database (MySQL)

- You must be able to explain some specifics about this infrastructure:
  - For every additional element, why you are adding it
  - What distribution algorithm your load balancer is configured with and how it works
  - Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both
  - How a database Primary-Replica (Master-Slave) cluster works
  - What is the difference between the Primary node and the Replica node in regard to the application

- You must be able to explain what the issues are with this infrastructure:
  - Where are SPOF
  - Security issues (no firewall, no HTTPS)
  - No monitoring

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-------------------

### [2. Secured And Monitored Web Infrastructure](https://github.com/MathieuMorel62/holbertonschool-system_engineering-devops/blob/main/web_infrastructure_design/2-secured_and_monitored_web_infrastructure.md)

On a whiteboard, design a three server web infrastructure that hosts the website `www.foobar.com`, it must be secured, serve encrypted traffic, and be monitored.
  
**Requirements:**

- You must add:
  - 3 firewalls
  - 1 SSL certificate to serve www.foobar.com over HTTPS
  - 3 monitoring clients (data collector for Sumologic or other monitoring services)

- You must be able to explain some specifics about this infrastructure:
  - For every additional element, why you are adding it
  - What are firewalls for
  - Why is the traffic served over HTTPS
  - What monitoring is used for
  - How the monitoring tool is collecting data
  - Explain what to do if you want to monitor your web server QPS

- You must be able to explain what the issues are with this infrastructure:
  - Why terminating SSL at the load balancer level is an issue
  - Why having only one MySQL server capable of accepting writes is an issue
  - Why having servers with all the same components (database, web server and application server) might be a problem

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-------------------

### [3. Scale Up](https://github.com/MathieuMorel62/holbertonschool-system_engineering-devops/blob/main/web_infrastructure_design/3-scale_up.md)

Readme

- [Application server vs web server](https://www.nginx.com/resources/glossary/application-server-vs-web-server/)

**Requirements:**

- You must add:
  - 1 server
  - 1 load-balancer (HAproxy) configured as cluster with the other one
  - Split components (web server, application server, database) with their own server

- You must be able to explain some specifics about this infrastructure:
  - For every additional element, why you are adding it
  
Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-------------------

## Author

- Mathieu Morel
