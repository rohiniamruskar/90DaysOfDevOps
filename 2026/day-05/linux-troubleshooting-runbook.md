# Linux Troubleshooting Runbook

## Target Service

Service inspected: SSH

---

# Environment Basics

## Check System Information

```bash
uname -a
```

Observed:
- Displayed Linux kernel and system architecture information.

---

## Check OS Version

```bash
cat /etc/os-release
```

Observed:
- Confirmed Ubuntu Linux distribution details.

---

# Filesystem Sanity Checks

## Create Test Directory

```bash
mkdir /tmp/runbook-demo
```

Observed:
- Temporary directory created successfully.

---

## Copy and Verify File

```bash
cp /etc/hosts /tmp/runbook-demo/hosts-copy
ls -l /tmp/runbook-demo
```

Observed:
- File copied correctly and visible in directory listing.

---

# CPU & Memory Checks

## Monitor Running Processes

```bash
top
```

Observed:
- CPU and memory usage looked normal.
- No abnormal spikes detected.

---

## Check Memory Usage

```bash
free -h
```

Observed:
- Available memory was sufficient.
- No memory pressure observed.

---

# Disk & IO Checks

## Check Disk Usage

```bash
df -h
```

Observed:
- Root partition had enough free space.

---

## Check Log Directory Size

```bash
du -sh /var/log
```

Observed:
- Log directory size was within normal range.

---

# Network Checks

## Check Listening Ports

```bash
ss -tulpn
```

Observed:
- SSH service listening on port 22.

---

## Test Network Connectivity

```bash
ping google.com
```

Observed:
- Network connectivity working successfully.

---

# Log Checks

## Check SSH Service Logs

```bash
journalctl -u ssh -n 20
```

Observed:
- No recent SSH service errors found.

---

## Check System Logs

```bash
tail -n 20 /var/log/syslog
```

Observed:
- System logs showed normal activity.

---

# Quick Findings

- SSH service running normally
- System resources healthy
- Network connectivity working
- No critical errors in logs

---

# If This Worsens

1. Restart SSH service using:

```bash
sudo systemctl restart ssh
```

2. Increase log monitoring using:

```bash
journalctl -u ssh -f
```

3. Investigate high CPU or memory usage using:

```bash
top
ps aux
```
