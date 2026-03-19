# Linux Networking – Deep Level Concepts
## 1. /etc/hosts File

The /etc/hosts file is a local DNS mapping file used by Linux to map hostnames to IP addresses manually.

Before the system queries a DNS server, it first checks the /etc/hosts file.

Why it exists

It allows you to resolve hostnames without using DNS servers.

Example
sudo nano /etc/hosts

Example entry:

127.0.0.1   localhost
192.168.1.10   myserver

Now you can access the server using:

ping myserver

Instead of:

ping 192.168.1.10
Real Use Cases

Local testing

Blocking websites

Internal server mapping

Development environments

Example blocking a website:

127.0.0.1 facebook.com
## 2. /etc/resolv.conf

This file defines DNS servers used by the system.

Whenever you try to access a domain like:

google.com

Linux checks /etc/resolv.conf to know which DNS server should resolve it.

View the file
cat /etc/resolv.conf

Example:

nameserver 8.8.8.8
nameserver 1.1.1.1

Meaning:

DNS Server	Provider
8.8.8.8	Google DNS
1.1.1.1	Cloudflare DNS
Important Concept

DNS Resolution flow:

Application
   ↓
/etc/hosts
   ↓
DNS Server (/etc/resolv.conf)
   ↓
Internet DNS
## 3. netstat

netstat is used to display network connections, routing tables, and listening ports.

Basic Command
netstat
Common Options
Command	Purpose
netstat -t	TCP connections
netstat -u	UDP connections
netstat -l	Listening ports
netstat -n	Show numeric addresses
netstat -p	Show process using port
Most Useful Command
netstat -tulnp

Example output:

tcp   0   0 0.0.0.0:22   0.0.0.0:*   LISTEN   1234/sshd

Meaning:

Column	Meaning
tcp	protocol
22	port
LISTEN	service waiting for connection
sshd	process running
Important

Modern Linux uses:

ss

Instead of netstat.

Example:

ss -tulnp
## 4. traceroute

traceroute shows the path packets take from your computer to a destination server.

Command
traceroute google.com

Example output:

1 192.168.1.1
2 10.0.0.1
3 172.217.167.78

Each line is a network hop (router).

Why it is useful

Used to diagnose:

network latency

packet loss

routing issues

Example problem:

If hop 5 fails → network problem exists there.

## 5. route

The route command displays or modifies the IP routing table.

The routing table tells Linux:

Where should packets go?

Command
route -n

Example output:

Destination   Gateway      Genmask
0.0.0.0       192.168.1.1  0.0.0.0

Meaning:

0.0.0.0 = default route
192.168.1.1 = gateway
Modern Alternative
ip route

Example:

ip route show
## 6. nslookup

nslookup is used to query DNS servers to resolve domain names.

Command
nslookup google.com

Output:

Server: 8.8.8.8
Address: 8.8.8.8#53

Name: google.com
Address: 142.250.183.206

Meaning:

DNS converted:

google.com → IP address
Query specific DNS server
nslookup google.com 8.8.8.8
## 7. ufw (Uncomplicated Firewall)

ufw is a simple firewall management tool for Linux.

It manages iptables rules in a simpler way.

Enable firewall
sudo ufw enable
Check status
sudo ufw status
Allow port

Example:

sudo ufw allow 22

Allow SSH.

Allow HTTP
sudo ufw allow 80
Block port
sudo ufw deny 21
## 8. iptables

iptables is the core Linux firewall system.

It controls incoming and outgoing network traffic using rules.

View rules
sudo iptables -L
Block an IP
sudo iptables -A INPUT -s 192.168.1.5 -j DROP

Meaning:

-A = append rule
INPUT = incoming traffic
-s = source IP
DROP = block packet
Allow SSH