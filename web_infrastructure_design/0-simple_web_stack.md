# To design a simple web infrastructure that hosts a website reachable via www.foobar.com, we will utilize a single server with the following components:
* 1 Server: This is a physical or virtual machine that hosts all the components necessary to run the website.
* 1 Web Server (Nginx): This software serves static content and forwards requests for dynamic content to the application server.
* 1 Application Server: This handles the application's business logic and processes requests from the web server.
* 1 Application Files (Code Base): The source code for the web application, which can include HTML, CSS, JavaScript, and server-side scripts.
* 1 Database (MySQL): This stores data for the application, allowing it to retrieve and manipulate information as needed.
* Domain Name (foobar.com): Configured with a www record pointing to the server's IP address (8.8.8.8).

### User Acess Flow
1. A user types www.foobar.com into their browser.
2. The browser sends a request to a DNS server to resolve the domain name to an IP address.
3. The DNS returns the IP address 8.8.8.8 associated with www.foobar.com.
4. The browser sends an HTTP request to the server at that IP address.

## Explanation of Infrastructure Components

#### What is a Server?
A server is a computer designed to process requests and deliver data to other computers over a network. It provides resources, services, and data to client machines.

#### Role of the Domain Name
The domain name serves as a human-readable address for accessing resources on the internet, translating complex numerical IP addresses into easy-to-remember names.

#### Type of DNS Record
The www in www.foobar.com is typically an A record, which maps the domain name to its corresponding IP address.

#### Role of the Web Server
The web server (Nginx) handles incoming HTTP requests from users' browsers, serving static files directly or passing dynamic requests to the application server for processing23.

#### Role of the Application Server
The application server executes business logic and processes requests from the web server, often interacting with the database to fetch or store data45.

#### Role of the Database
The database (MySQL) stores structured data for the application, allowing it to perform queries and transactions based on user interactions911.

#### Communication Protocol
The server communicates with users' computers using HTTP/HTTPS protocols, facilitating data transfer over the internet.

## Issues with This Infrastructure
1. Single Point of Failure (SPOF): If any component (web server, application server, or database) fails, it can take down the entire website since all operations rely on this single server.

2. Downtime During Maintenance: Updating or deploying new code often requires restarting services on the web server, leading to temporary unavailability of the site.

3. Scalability Limitations: As traffic increases, this single-server setup may struggle to handle multiple simultaneous requests efficiently, leading to slow response times or crashes under heavy load.

#### This simple web infrastructure is effective for small-scale applications but may require enhancements such as load balancing and redundancy for larger deployments.


https://drive.google.com/file/d/1MnUIYMios9bEEJ1-M7UZlOxOOAD4cQy9/view?usp=sharing
