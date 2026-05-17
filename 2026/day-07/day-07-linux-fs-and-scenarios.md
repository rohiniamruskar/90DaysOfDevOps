# Day 07 – Linux File System Hierarchy & Scenario Practice

# Part 1: Linux File System Hierarchy

## / (Root Directory)

- Starting point of the Linux file system
- All directories and files exist under root

```bash
ls -l /
```

Observed:
- Directories like `home`, `etc`, `var`, and `tmp`

I would use this when:
- Navigating the complete Linux file system

---

## /home

- Stores normal user home directories
- Contains user files and personal data

```bash
ls -l /home
```

Observed:
- User directories available inside `/home`

I would use this when:
- Accessing user files and scripts

---

## /root

- Home directory of the root user
- Used for administrative tasks

```bash
ls -l /root
```

Observed:
- Root user configuration and files

I would use this when:
- Performing system administration tasks

---

## /etc

- Stores configuration files
- Important system and service configs are stored here

```bash
ls -l /etc
```

Observed:
- Files like `hostname`, `hosts`, and `passwd`

I would use this when:
- Editing service or system configuration

---

## /var/log

- Stores system and application logs
- Very important for troubleshooting

```bash
ls -l /var/log
```

Observed:
- Log files like `syslog` and `auth.log`

I would use this when:
- Investigating system or service issues

---

## /tmp

- Stores temporary files
- Files may be deleted after reboot

```bash
ls -l /tmp
```

Observed:
- Temporary folders and files

I would use this when:
- Creating temporary test files

---

## /bin

- Contains essential Linux commands
- Commands needed during boot and recovery

```bash
ls -l /bin
```

Observed:
- Basic commands like `cat`, `ls`, and `cp`

I would use this when:
- Running basic Linux commands

---

## /usr/bin

- Contains additional user command binaries
- Most installed applications store binaries here

```bash
ls -l /usr/bin
```

Observed:
- Many executable commands available

I would use this when:
- Running installed applications

---

## /opt

- Used for optional or third-party applications

```bash
ls -l /opt
```

Observed:
- Optional software packages

I would use this when:
- Installing third-party tools

---

# Hands-on Tasks

## Find Largest Log Files

```bash
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
```

Observed:
- Identified large log files inside `/var/log`

---

## View Hostname Configuration

```bash
cat /etc/hostname
```

Observed:
- Displayed system hostname

---

## Check Home Directory

```bash
ls -la ~
```

Observed:
- Hidden files and user configuration files visible

---

# Part 2: Scenario-Based Practice

# Scenario 1: Service Not Starting

## Step 1

```bash
systemctl status myapp
```

Why:
- Checks whether service is active, failed, or stopped

---

## Step 2

```bash
journalctl -u myapp -n 50
```

Why:
- Displays recent service logs for troubleshooting

---

## Step 3

```bash
systemctl is-enabled myapp
```

Why:
- Verifies whether service starts automatically during boot

---

## Step 4

```bash
systemctl restart myapp
```

Why:
- Attempts to restart the failed service

---

# Scenario 2: High CPU Usage

## Step 1

```bash
top
```

Why:
- Shows live CPU and memory usage

---

## Step 2

```bash
ps aux --sort=-%cpu | head -10
```

Why:
- Displays top CPU-consuming processes

---

## Step 3

```bash
pgrep ssh
```

Why:
- Finds process ID of running service

---

# Scenario 3: Finding Service Logs

## Step 1

```bash
systemctl status ssh
```

Why:
- Confirms SSH service status

---

## Step 2

```bash
journalctl -u ssh -n 50
```

Why:
- Displays last 50 log lines for SSH service

---

## Step 3

```bash
journalctl -u ssh -f
```

Why:
- Monitors SSH logs in real time

---

# Scenario 4: File Permission Issue

## Step 1

```bash
ls -l /home/user/backup.sh
```

Why:
- Checks current file permissions

---

## Step 2

```bash
chmod +x /home/user/backup.sh
```

Why:
- Adds execute permission to script

---

## Step 3

```bash
ls -l /home/user/backup.sh
```

Why:
- Verifies execute permission added successfully

---

## Step 4

```bash
./backup.sh
```

Why:
- Runs the script after fixing permissions

---

# Key Learnings

- Learned important Linux directories and their purpose
- Practiced troubleshooting service issues
- Understood CPU and log investigation basics
- Learned how Linux permissions affect script execution
