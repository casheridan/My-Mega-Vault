## Introduction
---
The best thing to do before performing a pentest on a machine is to make a map of the nework "landscape" of the IP addresses. This allows us to see if the target is running any services before performing an attack.

When a machine starts a webserver or something similar it opens up a network construct called a port to recieve connections. Ports are necessary in order to make multiple connection or service requests. Network connections are made between two ports. Example: You open a webpage, your computer opens port 49534 to connect to the server's port 443.

Every computer has 65535 ports but many of them are registered as standard ports. Here are some examples of some of those standard ports:
- HTTP Webservice: Port 80
- HTTPS Webservice: Port 443
- Windows NETBIOS: Port 139
- SMB: 445

In a CTF setting these standard ports can be altered so it's more important to perform appropriate enumeration on the target.

To find out which ports the target has open we must do a port scan, this is to ensure we can perform a successful attack. To check how a port may respond, we can do it manually or with a tool like nmap. The port will respond in 3 ways: open, closed, or filtered (usually by a firewall). Once we know which ports are open, we can enumerate which services are running on each port manually or with nmap.

## Nmap Use Cases
---
- Syn Scan: -sS
- Detect target OS: -O
- Detect verion of services: -sV
- Verbosity: -v
- More verbosity (use this at least): -vv
- Save output in the 3 major formats: 