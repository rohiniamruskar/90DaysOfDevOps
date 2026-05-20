# Day 13 – Linux Volume Management (LVM)

# Task 1: Check Current Storage

## Check Block Devices

```bash
lsblk
```

![lsblk Output](images/lsblk-output.png)

---

## Check Physical Volumes

```bash
pvs
```

![PVS Output](images/pvs-output.png)

---

## Check Volume Groups

```bash
vgs
```

![VGS Output](images/vgs-output.png)

---

## Check Logical Volumes

```bash
lvs
```

![LVS Output](images/lvs-output.png)

---

## Check Disk Usage

```bash
df -h
```

![DF Output](images/df-output.png)

---

# Task 2: Create Physical Volume

## Create Virtual Disk

```bash
dd if=/dev/zero of=/tmp/disk1.img bs=1M count=1024
```

![Create Disk](images/create-disk.png)

---

## Attach Loop Device

```bash
losetup -fP /tmp/disk1.img
```

![Loop Setup](images/loop-setup.png)

---

## Verify Loop Device

```bash
losetup -a
```

![Loop Verify](images/loop-verify.png)

---

## Create Physical Volume

```bash
pvcreate /dev/loop0
```

![PV Create](images/pv-create.png)

---

## Verify Physical Volume

```bash
pvs
```

![PVS Verify](images/pvs-verify.png)

---

# Task 3: Create Volume Group

## Create Volume Group

```bash
vgcreate devops-vg /dev/loop0
```

![VG Create](images/vg-create.png)

---

## Verify Volume Group

```bash
vgs
```

![VGS Verify](images/vgs-verify.png)

---

# Task 4: Create Logical Volume

## Create Logical Volume

```bash
lvcreate -L 500M -n app-data devops-vg
```

![LV Create](images/lv-create.png)

---

## Verify Logical Volume

```bash
lvs
```

![LVS Verify](images/lvs-verify.png)

---

# Task 5: Format and Mount

## Format Logical Volume

```bash
mkfs.ext4 /dev/devops-vg/app-data
```

![Format Volume](images/format-volume.png)

---

## Create Mount Directory

```bash
mkdir -p /mnt/app-data
```

![Mount Directory](images/mount-directory.png)

---

## Mount Logical Volume

```bash
mount /dev/devops-vg/app-data /mnt/app-data
```

![Mount Volume](images/mount-volume.png)

---

## Verify Mounted Storage

```bash
df -h /mnt/app-data
```

![Mounted Verify](images/mounted-verify.png)

---

# Task 6: Extend the Volume

## Extend Logical Volume

```bash
lvextend -L +200M /dev/devops-vg/app-data
```

![Extend Volume](images/extend-volume.png)

---

## Resize Filesystem

```bash
resize2fs /dev/devops-vg/app-data
```

![Resize Filesystem](images/resize-filesystem.png)

---

## Verify Extended Storage

```bash
df -h /mnt/app-data
```

![Extended Verify](images/extended-verify.png)

---

# Commands Used

```bash
lsblk
pvs
vgs
lvs
df -h
pvcreate
vgcreate
lvcreate
mkfs.ext4
mount
lvextend
resize2fs
```

---

# What I Learned

- How Linux LVM works
- Difference between PV, VG, and LV
- How to create and mount logical volumes
- How to extend storage without repartitioning
- Importance of flexible storage management in Linux
