# Day 13 – Linux Volume Management (LVM)

## Task
Learn LVM to manage storage flexibly – create, extend, and mount volumes.

---

### Task 1: Create a virtul disk

Firt we need to switch to the root user by using command:  sudo su

Then we can create a virtula disk by using the below command

```bash
dd if=/dev/zero of=/tmp/disk1.img bs=1M count=1024
losetup -fP /tmp/disk1.img
losetup -a   # Note the device name (e.g., /dev/loop0)
```

### Task 2: Create a physical volume
```bash
pvcreate /dev/loop0    # To create a Phyiscal volume
pvs    # To check the details of Phyiscal volume 
```

### Task 3: Create Volume Group
```bash
vgcreate devops_vg /dev/loop0    # To create a vloume group
vgs    # To check the details of vloume group
```

### Task 4: Create Logical Volume
```bash
lvcreate -L 500M -n app-data devops_vg    # To create a logical volume
lvs     # To check the details of logical volume
```

### Task 5: Format and Mount
```bash
mkdir -p /mnt/app-data 
mkfs -t ext4 /dev/devops_vg/app-data
mount /dev/devops_vg/app-data /mnt/app-data
df -h /mnt/app-data
```

### Task 6: Extend the Volume
```bash
lvextend -L +200M /dev/devops_vg/app-data
df -h /mnt/app-data
```
