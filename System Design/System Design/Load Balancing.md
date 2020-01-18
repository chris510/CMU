# Load Balancing

Created By: Chris Trinh
Last Edited: Jan 17, 2020 3:22 PM

- What is load balancing and what is it for?
    - process of distributing network traffic across multiple servers and ensure that no single server bears too much demand by spreading the work evenly.
- What is a load balancer and what does it do?
    - A critical component in a distributed system that helps spread traffic across a cluster of servers to improve responsiveness and availability of the apps, websites, or databases.
    - It also keeps track of the resources available while distributing the request.
    - reducing individual server load and prevents any one server from failing
- Where does the load balancer sit in components?
    - Between the client/internet and servers.
- Where are the three places we can place the load balancers?
    1. Between user and web server
    2. Between web server and internal layer (application or cache servers)
    3. Between internal platform layer and database
- What are the benefits of a load balancing?
    1. Users experience faster and uninterrupted services because they don't have to wait for a server to finish a task and the request will be passed on to another source
    2. Higher throughput and less downtime from service providers. Since there are multiple servers, if a server is full then the load balancer will redirect  to an available one.
    3. Easier for system admins to handle incoming request while decreasing wait time for users
    4. Smart load balancers have predictive analytics to determine the potential bottle necks in traffic.
    5. Fewer failed and stressed components; instead of a single device doing loads of work, its split into many systems.

- What two factors load balancers use to determine the back end server?
    - Algorithms to determine the server is good enough to respond to requests and then to select one of the available servers
- What is a health check?
    - A way to monitor the status of a server by regularly connecting to them to make sure it works. If it fails, its automatically removed from the pool and no request will be forwarded to it until it passes the checks
- What is the least connection method?
    - directs traffic to server with least active connections. Useful when there are large clients and unevenly distributed servers
- What is the least response time method?
    - Traffic to the server with fewest active connections and lowest average response time.
- What is the least bandwidth method?
    - Selects the server that is serving the least amount of traffic using megabits per second (Mbps)
- What is the round robin method?
    - Cycles through a list and sends a request to each server.
- What is the weighted round robin method
    - Ranks the server based on capabilities and sends the more capable servers that has a 'higher weight' the connections first.
- What is IP hash?
    - hash of IP address of client is calculated and redirects the request to a server
- Why should we have redundant load balancers?
    - A load balancer can be the point of failure since there is one. If we have a second one and connect it to form a cluster. If the main one fails, the second load balance can take over.
- What are SSL's and what do they do?
- What is SSL termination?
    - Transition process where data traffic becomes encrypted and uncrypted
- How does SSL termination affect security?
    - Traffic between load balancers and web servers are not encrypted and can be exposed to an attack but risk is less when load balancer and web server are in the same data center
    - What is a solution to this?
        - Load balancer passes an encrypted request to the web server and it does the decryption (uses more CPU power)

- What does DDoS stand for?
    - Distributed denial-of-service attacks
- What is the off-loading function of a load balancer and how does it defend against DDoS attacks?
    - Off-loading is the method by shifting attack traffic from the corporate server to the public cloud provider
- Why software load balancers over perimeter firewall?
    - Load balancers are cheaper while firewalls require maintenance