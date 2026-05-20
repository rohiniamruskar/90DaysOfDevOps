# Day 14 – Networking Fundamentals & Hands-on Checks

# OSI Model vs TCP/IP Model

## OSI Model

- Layer 1 → Physical
- Layer 2 → Data Link
- Layer 3 → Network
- Layer 4 → Transport
- Layer 5 → Session
- Layer 6 → Presentation
- Layer 7 → Application

---

## TCP/IP Model

- Link Layer
- Internet Layer
- Transport Layer
- Application Layer

---

# Protocol Placement

| Protocol | Layer |
|---|---|
| IP | Network / Internet |
| TCP & UDP | Transport |
| HTTP & HTTPS | Application |
| DNS | Application |

---

# Real Example

```text
curl https://example.com
```

Application Layer (HTTP/HTTPS) → TCP → IP

---

# Hands-on Networking Checks

# Identity Check

## Check IP Address

```bash
hostname -I
```

Observed:
- Displayed private IP address of the server.

---

# Reachability Check

## Ping Target Host

```bash
ping google.com
```

Observed:
- Packets successfully received.
- Low latency and no packet loss observed.

---

# Path Check

## Trace Route

```bash
tracepath google.com
```

Observed:
- Displayed network hops between local machine and target host.

---

# Port Check

## Check Listening Ports

```bash
ss -tulpn
```

Observed:
- SSH service listening on port 22.

---

# DNS Resolution Check

## Resolve Domain Name

```bash
nslookup google.com
```

Observed:
- Domain successfully resolved to IP address.

---

# HTTP Check

## Check HTTP Headers

```bash
curl -I https://google.com
```

Observed:
- Received HTTP 200 response.

---

# Connection Snapshot

## View Network Connections

```bash
netstat -an | head
```

Observed:
- LISTEN and ESTABLISHED connections visible.

---

# Mini Task – Port Probe & Interpretation

## Probe SSH Port

```bash
nc -zv localhost 22
```

Observed:
- Port 22 reachable successfully.

Next Check If Failed:
- Check service status
- Verify firewall rules
- Verify listening ports

---

# Reflection

## Which Command Gives Fastest Signal During Issue?

```bash
ping
```

Reason:
- Quickly checks basic network connectivity.

---

# What Layer Would You Check If DNS Fails?

- Application Layer
- DNS configuration and resolver settings

---

# What Layer Would You Check For HTTP 500 Error?

- Application Layer
- Web server logs and backend application

---

# Two Follow-Up Checks During Real Incident

## Check Service Status

```bash
systemctl status nginx
```

---

## Check Logs

```bash
journalctl -u nginx
```

---

# What I Learned

- Learned basic networking troubleshooting workflow
- Understood OSI and TCP/IP models
- Practiced connectivity, DNS, and port checks
- Learned how to inspect listening services and HTTP responses
