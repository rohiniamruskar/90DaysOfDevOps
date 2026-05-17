# Linux Architecture Notes

## Core Components of Linux

### Kernel
- Core part of Linux OS
- Manages CPU, memory, devices, and processes
- Acts as bridge between hardware and software

### User Space
- Area where users and applications run
- Commands like `ls`, `top`, `vim` run in user space

### systemd / init
- First process started during boot (PID 1)
- Manages services and startup processes
- Handles logs and service restarts

---

# Process Management

## What is a Process?
A process is a running program in Linux.

Example:
- nginx
- docker
- ssh

Each process has:
- PID (Process ID)
- memory usage
- CPU usage
- process state

---

# Process States

| State | Meaning |
|---|---|
| Running | Process currently executing |
| Sleeping | Waiting for event/input |
| Stopped | Process paused |
| Zombie | Process finished but entry still exists |

---

# Useful Linux Commands

## Check Running Processes

```bash
ps aux
```

## Real-Time Process Monitoring

```bash
top
```

## View Service Status

```bash
systemctl status nginx
```

## Restart Service

```bash
sudo systemctl restart nginx
```

## View Logs

```bash
journalctl -u nginx
```

---

# Why systemd Matters in DevOps

- Automatically starts services during boot
- Restarts failed services
- Helps troubleshoot applications
- Centralized logging using journalctl

---

# Key Learnings

- Linux kernel manages system resources
- Processes are controlled using PID and states
- systemd is important for service management
- Linux troubleshooting is essential for DevOps
