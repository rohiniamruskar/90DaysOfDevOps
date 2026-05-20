# Day 12 – Revision Notes

# Mindset & Learning Plan Review

- Reviewed Linux fundamentals from Days 01–11
- Focus remains on DevOps fundamentals and hands-on practice
- Need more practice on permissions and troubleshooting commands

---

# Processes & Services Revision

## Check Running Processes

```bash
ps aux
```

Observed:
- Multiple system processes running normally

---

## Check SSH Service Status

```bash
systemctl status ssh
```

Observed:
- SSH service active and running successfully

---

## View SSH Logs

```bash
journalctl -u ssh -n 10
```

Observed:
- Recent SSH login logs displayed correctly

---

# File Skills Practice

## Append Text to File

```bash
echo "DevOps Revision" >> notes.txt
```

---

## Change File Permission

```bash
chmod 644 notes.txt
```

---

## Check File Ownership

```bash
ls -l notes.txt
```

Observed:
- Verified permission and ownership successfully

---

# Cheat Sheet Refresh

## 5 Commands I Would Use First During Incident

```bash
top
ps aux
systemctl status
journalctl -u
df -h
```

Why:
- Useful for checking CPU, memory, services, logs, and disk space quickly

---

# User & Group Revision

## Create User

```bash
sudo useradd -m revision-user
```

---

## Verify User

```bash
id revision-user
```

Observed:
- User created successfully with UID and GID

---

# Mini Self-Check

## Which 3 Commands Save You Most Time?

### 1. top
- Helps monitor CPU and memory usage quickly

### 2. systemctl status
- Quickly checks service health

### 3. journalctl -u
- Useful for troubleshooting logs

---

# How to Check Service Health?

## Commands

```bash
systemctl status ssh
journalctl -u ssh -n 20
ps aux
```

These commands help verify:
- service status
- running processes
- recent logs

---

# How to Safely Change Ownership & Permissions?

## Example Command

```bash
sudo chown ubuntu:ubuntu notes.txt

chmod 644 notes.txt
```

Why:
- Ensures correct owner and safe read/write permissions

---

# Focus for Next 3 Days

- More Linux troubleshooting practice
- Faster command-line usage

---

# Key Takeaways

- Linux commands require regular practice
- Logs are important during troubleshooting
- Permissions and ownership are critical in Linux
- Process and service management are core DevOps skills
