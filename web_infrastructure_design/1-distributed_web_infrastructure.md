# To design a three-server web infrastructure for www.foobar.com, we'll use the following components:
* 2 servers (in addition to the existing one)
* 1 web server (Nginx)
* 1 application server
* 1 load-balancer (HAproxy)
* 1 set of application files (code base)
* 1 database (MySQL)
## Infrastructure Design
### Server 1 (Primary):
* Nginx web server
* Application server
* MySQL database (Primary)
* Application files
### Server 2 (Secondary):
* Nginx web server
* Application server
* MySQL database (Replica)
* Application files
### Server 3 (Load Balancer):
* HAproxy
## Specifics of the * Infrastructure
1. Additional Elements
Two extra servers: Added for redundancy and improved performance, allowing distribution of the workload1.
2. Load balancer (HAproxy): Distributes incoming traffic across multiple servers, improving performance and reliability.
## Load Balancer Configuration
The HAproxy load balancer is configured with a Round Robin algorithm. This method distributes incoming requests sequentially to each server in a circular fashion, ensuring an equal distribution of traffic.
## Active-Active Setup
This infrastructure uses an Active-Active setup. In this configuration, all servers actively handle requests simultaneously, improving performance and providing better resource utilization compared to Active-Passive setups.
## Database Primary-Replica Cluster
The MySQL database uses a Primary-Replica (Master-Slave) cluster. The Primary node handles write operations and replicates data to the Replica node. The Replica node can handle read operations, improving performance and providing data redundancy.
## Primary vs. Replica Node
The Primary node handles write operations and is the authoritative source of data. The Replica node receives updates from the Primary and can handle read operations, reducing the load on the Primary node.
### Issues with this Infrastructure
1. Single Point of Failure (SPOF): The load balancer remains a potential SPOF. If it fails, the entire system becomes inaccessible.
2. Security Issues:
No firewall: The infrastructure is vulnerable to unauthorized access and potential attacks1.
No HTTPS: Data transmission is not encrypted, risking data interception.
3. No Monitoring: Without proper monitoring, it's difficult to detect and respond to performance issues, security threats, or system failures promptly.
