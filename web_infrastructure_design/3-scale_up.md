# To enhance the infrastructure for www.foobar.com, we'll implement the following changes:
1. Add 1 server, bringing the total to 4 servers
2. Add 1 load-balancer (HAproxy) configured as a cluster with the existing one
3. Split components (web server, application server, database) onto separate servers
## Infrastructure Design
##### 1.  Web Server:
* Nginx for serving static content and routing requests
##### 2.  Application Server:
* Hosts the application logic and processes dynamic content
##### 3.  Database Server:
* Dedicated MySQL server for data storage and management
##### 4.  Load Balancer Cluster:
* Two HAproxy instances configured in an active-active cluster
## Explanation of Additional Elements
##### 1. Additional Server:
Added to allow for component separation, improving resource allocation and scalability. This separation enables independent optimization and scaling of each component.
##### 2. Load Balancer Cluster:
Implementing a second load balancer in an active-active configuration improves fault tolerance and increases the overall capacity to handle incoming traffic. This setup allows for better distribution of requests and eliminates a single point of failure.
##### 3. Component Separation:
* Web Server: Dedicated to handling HTTP requests and serving static content efficiently.
* Application Server: Focuses on processing business logic and generating dynamic content, allowing for better resource utilization.
* Database Server: Isolates data management, improving performance and security of database operations.

This infrastructure design enhances scalability, performance, and reliability by allowing each component to be optimized and scaled independently based on specific requirements.



###### - TTL (Time To Live) is a value that determines how long data or packets should exist in a system before being discarded or updated. In networking contexts, TTL serves several important purposes:
1. In IP packets: TTL indicates the number of hops a packet can make before being discarded, preventing endless circulation in the network.
2. In DNS records: TTL specifies how long DNS information should be cached by resolving name servers, affecting the propagation time of DNS changes.
3. In CDN caching: TTL determines how long content should be served from a CDN edge server before fetching a new copy from the origin server.
##### TTL values vary depending on the context:
* For critical DNS records or those with dynamic updates: 30 seconds to 5 minutes.
* For less critical DNS records: 1 to 12 hours.
* For stable DNS records (e.g., web server or CDN): 12 hours to 1 day.
* For proxied records in Cloudflare: Default "Auto" setting of 300 seconds (5 minutes).
##### Choosing appropriate TTL values involves balancing factors such as cache efficiency, update propagation speed, and query costs.
