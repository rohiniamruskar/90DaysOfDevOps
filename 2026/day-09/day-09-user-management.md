# Day 09 Challenge

# Users & Groups Created

## Users
- tokyo
- berlin
- professor
- nairobi

## Groups
- developers
- admins
- project-team

---

# Task 1: Create Users

## Commands Used

```bash
sudo useradd -m tokyo
sudo passwd tokyo

sudo useradd -m berlin
sudo passwd berlin

sudo useradd -m professor
sudo passwd professor
```

## Verification

```bash
cat /etc/passwd
ls -l /home
```

---

# Task 2: Create Groups

## Commands Used

```bash
sudo groupadd developers
sudo groupadd admins
```

## Verification

```bash
cat /etc/group
```

---

# Task 3: Assign Users to Groups

## Commands Used

```bash
sudo usermod -aG developers tokyo

sudo usermod -aG developers,admins berlin

sudo usermod -aG admins professor
```

## Verification

```bash
groups tokyo
groups berlin
groups professor
```

---

# Task 4: Shared Directory

## Create Directory

```bash
sudo mkdir -p /opt/dev-project
```

## Change Group Owner

```bash
sudo chgrp developers /opt/dev-project
```

## Set Permissions

```bash
sudo chmod 775 /opt/dev-project
```

## Test File Creation

```bash
sudo -u tokyo touch /opt/dev-project/tokyo-file.txt

sudo -u berlin touch /opt/dev-project/berlin-file.txt
```

## Verification

```bash
ls -ld /opt/dev-project
ls -l /opt/dev-project
```

---

# Task 5: Team Workspace

## Create User

```bash
sudo useradd -m nairobi
sudo passwd nairobi
```

## Create Group

```bash
sudo groupadd project-team
```

## Add Users to Group

```bash
sudo usermod -aG project-team nairobi
sudo usermod -aG project-team tokyo
```

## Create Workspace Directory

```bash
sudo mkdir -p /opt/team-workspace
```

## Set Group & Permissions

```bash
sudo chgrp project-team /opt/team-workspace

sudo chmod 775 /opt/team-workspace
```

## Test File Creation

```bash
sudo -u nairobi touch /opt/team-workspace/nairobi-file.txt
```

## Verification

```bash
ls -ld /opt/team-workspace
ls -l /opt/team-workspace
```

---

# Commands Used

```bash
useradd
passwd
groupadd
usermod
groups
chmod
chgrp
touch
ls
```

---

# What I Learned

- How to create Linux users and groups
- How Linux group permissions work
- How shared directories are managed
- Importance of permissions in DevOps environments
