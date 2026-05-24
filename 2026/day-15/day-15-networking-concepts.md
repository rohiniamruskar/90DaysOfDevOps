# Day 15 – Networking Concepts: DNS, IP, Subnets & Ports

# Task 1: DNS – How Names Become IPs

## What Happens When You Type google.com?

1. Browser checks local DNS cache.
2. If not found, request goes to DNS resolver.
3. DNS server returns IP address of google.com.
4. Browser connects to that IP and loads the website.

---

## DNS Record Types

### A Record
Maps domain name to IPv4 address.

### AAAA Record
Maps domain name to IPv6 address.

### CNAME
Maps one domain to another domain.

### MX
Specifies mail server for email delivery.

### NS
Specifies authoritative DNS servers.

---

## Check DNS Resolution

```bash
dig google.com
```

Observed:
- Identified A record from ANSWER SECTION
- Checked TTL value

Example:

```text
google.com 300 IN A 142.250.xx.xx
```

---

# Task 2: IP Addressing

## What is IPv4?

IPv4 is a 32-bit address used to identify devices in a network.

Example:

```text
192.168.1.10
```

Structure:
- Four octets
- Range 0–255

---

## Public vs Private IP

Public IP:
- Accessible over internet

Example:

```text
18.x.x.x
```

Private IP:
- Used inside local network

Example:

```text
192.168.1.20
```

---

## Private IP Ranges

```text
10.0.0.0 – 10.255.255.255

172.16.0.0 – 172.31.255.255

192.168.0.0 – 192.168.255.255
```

---

## Check Local IP

```bash
ip addr show
```

Observed:
- Found private IP assigned to server.

---

# Task 3: CIDR & Subnetting

## What Does /24 Mean?

```text
192.168.1.0/24
```

Means:
- 24 bits for network
- Remaining bits for hosts

---

## Why Do We Subnet?

- Better IP management
- Reduce broadcast traffic
- Improve network organization

---

## CIDR Table

| CIDR | Subnet Mask | Total IPs | Usable Hosts |
|---|---|---:|---:|
| /24 | 255.255.255.0 | 256 | 254 |
| /16 | 255.255.0.0 | 65536 | 65534 |
| /28 | 255.255.255.240 | 16 | 14 |

---

# Task 4: Ports – The Doors to Services

## What is a Port?

Ports allow multiple services to communicate using one IP address.

---

## Common Ports

| Port | Service |
|---|---|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |
| 53 | DNS |
| 3306 | MySQL |
| 6379 | Redis |
| 27017 | MongoDB |

---

## Check Listening Ports

```bash
ss -tulpn
```

Observed:
- Port 22 → SSH
- Port 80 → HTTP

---

# Task 5: Putting It Together

## curl http://myapp.com:8080

Networking concepts involved:

- DNS resolves domain to IP
- HTTP request sent using TCP
- Communication occurs through port 8080

---

## App Cannot Reach Database (10.0.1.50:3306)

Checks:

1. Verify database service status
2. Check port accessibility
3. Verify network/firewall rules

Example:

```bash
ping 10.0.1.50

ss -tulpn

nc -zv 10.0.1.50 3306
```

---

# Commands Used

```bash
dig google.com
ip addr show
ss -tulpn
ping
nc
```

---

# What I Learned

- How DNS converts names into IP addresses
- Difference between public and private IP
- CIDR and subnet basics
- Importance of ports in networking
- Basic troubleshooting flow for connectivity issues
