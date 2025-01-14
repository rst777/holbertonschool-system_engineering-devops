# To design a secure, encrypted, and monitored three-server web infrastructure for www.foobar.com, we'll include the following components:
* 3 servers
* 1 load balancer (HAproxy)
* 3 firewalls
* 1 SSL certificate
* 3 monitoring clients
* Web servers (Nginx)
* Application servers
* Database (MySQL)
## Infrastructure Design
1. ##### Server 1, Server 2, Server 3:
* Nginx web server
* Application server
* MySQL database
* Firewall
* Monitoring client
2. ##### Load Balancer:
* HAproxy for distributing traffic
3. ##### SSL Certificate:
* Applied to encrypt traffic for www.foobar.com
## Additional Elements Explanation
### Firewalls
Firewalls are added to enhance security by controlling incoming and outgoing network traffic based on predetermined security rules. They act as a barrier between trusted internal networks and untrusted external networks.
### SSL Certificate
An SSL certificate is implemented to serve www.foobar.com over HTTPS, encrypting data in transit between the client and the server. This protects sensitive information from interception and tampering.
### Monitoring Clients
Monitoring clients are added to collect data on the infrastructure's performance, health, and security. They help in identifying issues, optimizing performance, and ensuring the system's reliability.
## Specifics of the Infrastructure
### Firewall Purpose
Firewalls protect the network from unauthorized access, malicious traffic, and potential cyber threats.
### HTTPS Traffic
Traffic is served over HTTPS to encrypt data transmission, ensuring confidentiality and integrity of information exchanged between users and the website.
### Monitoring Purpose
Monitoring is used to track the performance, availability, and security of the infrastructure. It helps in detecting and resolving issues quickly, optimizing resource utilization, and maintaining service quality.
### Monitoring Data Collection
Monitoring tools collect data through agents installed on servers, log analysis, and network traffic inspection. They gather metrics on CPU usage, memory utilization, request rates, error rates, and other key performance indicators.
## Monitoring Web Server QPS
### To monitor web server Queries Per Second (QPS):
1. Use monitoring tools like Apache Benchmark or JMeter to simulate load.
2. Analyze server logs to count requests over time.
3. Implement real-time monitoring with tools like Grafana and Prometheus.
4. Calculate QPS by dividing the total number of requests by the time period in seconds.
## Issues with this Infrastructure
1. SSL Termination at Load Balancer: Terminating SSL at the load balancer level can expose decrypted data within the internal network, potentially compromising security.
2. Single MySQL Write Server: Having only one MySQL server capable of accepting writes creates a single point of failure for write operations and limits write scalability.
3. Homogeneous Server Components: Having servers with identical components (database, web server, and application server) can lead to resource contention and makes it difficult to optimize each component independently. It also increases the impact of a single type of failure across the entire infrastructure.
