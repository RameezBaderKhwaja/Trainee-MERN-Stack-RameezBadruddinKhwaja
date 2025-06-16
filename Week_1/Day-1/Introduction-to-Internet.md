Network & Internet
A network connects devices (e.g., your home Wi‑Fi). When networks connect to other networks, we get the Internet, a global system of networks 


Packet
Data is sent in small chunks called packets. Each packet carries a header (with origin/destination info) and payload (actual content) 


TCP/IP Model – 4 Layers
Application Layer
Where your code runs (HTTP, DNS).

Transport Layer
TCP ensures reliable data delivery; UDP is faster but less reliable .

Internet Layer
Uses IP addresses to route packets between networks 


Link Layer
Handles local network communication (Wi‑Fi, Ethernet) 


Network Interfaces
Devices have interfaces like eth0, wlan0, or lo (loopback).

Servers may use multiple interfaces: one for internet traffic, another for internal LAN 


Routing & IP
Every packet uses routing tables to find the next step on its path.

End-wired devices use default gateways (usually ISP routers).

Larger networks (data centers, ISPs) use BGP for routing across the internet. 


DNS, HTTP, HTTPS, SSL/TLS
DNS translates human-friendly names to IP addresses.

HTTP/HTTPS handle web requests.

SSL/TLS encrypts data in transit 

Security & Firewalls
Firewalls block or allow traffic based on rules.

NAT (Network Address Translation) lets many devices share one IP.

VPN simulates secure LANs over public networks 


Your browser (app layer) sends an HTTP request.

TCP ensures packets arrive in order.

IP routes packets via routers and interfaces.

DNS helps browsers find the server's IP.

Firewalls/NAT/VPN control or secure access routes.

SSL/TLS encrypts sensitive data.