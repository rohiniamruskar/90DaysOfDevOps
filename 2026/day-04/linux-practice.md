# Linux Practice Notes

## Process Checks

### Check Running Processes

```bash
ps aux
```

Used to view all running processes in the system.

---

### Real-Time Process Monitoring

```bash
top
```

Shows CPU and memory usage of running processes.

---

# Service Checks

## Check SSH Service Status

```bash
systemctl status ssh
```

Verified that SSH service is active and running.

---

## List Running Services

```bash
systemctl list-units --type=service
```

Used to view active system services.

---

# Log Checks

## Check SSH Logs

```bash
journalctl -u ssh
```

Viewed SSH service logs using journalctl.

---

## View Recent System Logs

```bash
tail -n 20 /var/log/syslog
```

Displayed the latest 20 log entries from system logs.

---

# Mini Troubleshooting Practice

## Restart SSH Service

```bash
sudo systemctl restart ssh
```

Restarted SSH service successfully.

---

## Verify Service After Restart

```bash
systemctl status ssh
```

Confirmed SSH service is running properly after restart.
---

# Key Learnings

- Learned how to inspect running processes
- Practiced checking Linux services using systemctl
- Viewed logs using journalctl and tail
- Understood basic troubleshooting workflow
