# Linux Day 03 - Networking Basics
## 1. What is Networking in Linux?

Networking in Linux allows a system to communicate with other systems over a network or the internet.

It enables:

Communication between servers

Access to websites and APIs

Data transfer between machines

Cloud infrastructure communication

In cloud environments like AWS EC2, networking allows instances to communicate using IP addresses and ports.

## 2. Important Networking Concepts
1. IP Address

An IP Address is a unique identifier assigned to a machine in a network.

Example:

192.168.1.10

Types:

Private IP → Used inside internal networks

Public IP → Used on the internet

## 2. Network Interface

A Network Interface is the connection point between a device and a network.

Examples:

eth0

ens5

lo (loopback)

## 3. Ports

Ports allow multiple services to run on one machine.

Examples:

SSH → 22

HTTP → 80

HTTPS → 443

## 4. DNS (Domain Name System)

DNS converts domain names into IP addresses.

Example:

google.com → 142.250.183.14

## 3. Check IP Address

Command used:

ip a

Purpose:

Displays all network interfaces and their IP addresses.

Example Output:

2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP>
    inet 192.168.1.10/24

Important Fields:

Field	Meaning
eth0	Network interface
inet	IPv4 address
/24	Subnet mask
## 4. Check Routing Table

Command:

ip route

Purpose:

Shows the routing table, which determines how packets travel across networks.

Example:

default via 192.168.1.1 dev eth0

Meaning:

Default gateway → 192.168.1.1

Network interface → eth0

## 5. Testing Network Connectivity

Command:

ping google.com

Purpose:

Checks if a system can reach another host over the network.

Example:

ping 8.8.8.8

Stop ping using:

CTRL + C
## 6. Checking Open Ports and Services

Command:

ss -tulnp

Purpose:

Displays open ports and running services.

Options:

Option	Meaning
-t	TCP connections
-u	UDP connections
-l	Listening ports
-n	Show numeric addresses
-p	Show process using the port

Example Output:

tcp LISTEN 0 128 0.0.0.0:22

Meaning:

SSH service is listening on port 22.

## 7. DNS Tools
nslookup

Command:

nslookup google.com

Purpose:

Find the IP address of a domain name.

Example Output:

Name: google.com
Address: 142.250.183.14
dig (Advanced DNS Tool)

Command:

dig google.com

Purpose:

Provides detailed DNS information, including:

DNS server

Query time

IP address

Authority section

## 8. Testing Web Requests

Command:

curl google.com

Purpose:

Used to transfer data from servers and test web requests.

Common use in DevOps:

Testing APIs

Checking website responses

Debugging services

Example:

curl https://api.github.com
## 9. Network Interfaces

Command:

ip link

Purpose:

Displays network interface information.

Example Output:

1: lo
2: eth0
Interface	Meaning
lo	Loopback interface
eth0	Network interface
## 10. Restart Network Service

Command:

sudo systemctl restart networking

Purpose:

Restarts the networking service when:

Network configuration changes

Connection issues occur

Interfaces need to reload

Check service status:

systemctl status networking
## 11. Commands Practiced

Commands I practiced today:

ip a
ip route
ping google.com
ss -tulnp
nslookup google.com
dig google.com
curl google.com
ip link
sudo systemctl restart networking
## 12. Why Networking is Important for DevOps

Networking knowledge is critical for:

Cloud infrastructure

Kubernetes networking

Load balancers

Microservices communication

Debugging production issues

Without networking knowledge, cloud and DevOps engineering is impossible.

## 13. Reflection

Today I learned how Linux systems communicate with other machines using IP addresses, ports, and DNS.

I practiced commands to:

Check IP addresses

View routing tables

Test connectivity

Check open ports

Perform DNS lookups

I now understand the basics of Linux networking, but I still need more hands-on practice to quickly troubleshoot network issues.