LOAD BALANCER

A Load Balancer is a device or software that distributes incoming network traffic across multiple servers so that no single server becomes overloaded.

Why use a Load Balancer?

Imagine a website has 3 servers:

Users
  |
Load Balancer
 /    |    \
Server1 Server2 Server3

Instead of all users connecting to Server1, the load balancer spreads requests among all servers.

Benefits

✅ Improved Performance

Traffic is shared across multiple servers.

✅ High Availability

If one server fails, traffic is redirected to healthy servers.

✅ Scalability

New servers can be added easily when traffic increases.


Common Load Balancing Algorithms
1. Round Robin

Requests are sent one after another:

Request 1 → Server1
Request 2 → Server2
Request 3 → Server3
Request 4 → Server1
2. Least Connections

Sends traffic to the server with the fewest active connections.

3. Weighted Round Robin

More powerful servers receive more traffic.

Server1 Weight = 3
Server2 Weight = 1

Server1 gets 3 times more requests.


Types of Load Balancers
Layer 4 (Transport Layer)

Works with:

TCP
UDP

Makes decisions based on:

IP Address
Port Number
Layer 7 (Application Layer)

Works with:

HTTP
HTTPS

Can route based on:

URL
Cookies
Headers

Example:

example.com/images → Image Server
example.com/api → API Server
Popular Load Balancers
NGINX
HAProxy
Traefik
AWS Elastic Load Balancing
Cloudflare Load Balancing

✅ Security

Can hide backend servers and provide DDoS protection.
