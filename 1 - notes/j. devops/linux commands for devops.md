---
status: newBorn
related-links: 
created: 2025-05-30T22:09
updated: 2025-05-30T22:09
---

### File Management Commands

#### `ls`
**Description:** Lists directory contents.  
**Example:**
```bash
ls -la
```

#### `cp`
**Description:** Copies files or directories.  
**Example:**
```bash
cp source.txt destination.txt
```

#### `mv`
**Description:** Moves or renames files or directories.  
**Example:**
```bash
mv oldname.txt newname.txt
```

#### `rm`
**Description:** Removes files or directories.  
**Example:**
```bash
rm file.txt
```

#### `mkdir`
**Description:** Creates directories.  
**Example:**
```bash
mkdir new_folder
```

#### `touch`
**Description:** Creates empty files or updates file timestamps.  
**Example:**
```bash
touch newfile.txt
```

---

### Process Management Commands

#### `ps`
**Description:** Displays information about active processes.  
**Example:**
```bash
ps aux
```

#### `top`
**Description:** Displays real-time system processes.  
**Example:**
```bash
top
```

#### `kill`
**Description:** Terminates processes.  
**Example:**
```bash
kill 1234
```

#### `nice`
**Description:** Runs a command with adjusted priority.  
**Example:**
```bash
nice -n 10 myscript.sh
```

#### `renice`
**Description:** Alters the priority of a running process.  
**Example:**
```bash
renice 15 -p 1234
```

---

### User Management Commands

#### `useradd`
**Description:** Creates a new user account.  
**Example:**
```bash
useradd newuser
```

#### `userdel`
**Description:** Deletes a user account.  
**Example:**
```bash
userdel olduser
```

#### `passwd`
**Description:** Changes a user's password.  
**Example:**
```bash
passwd newuser
```

#### `su`
**Description:** Switches users.  
**Example:**
```bash
su - newuser
```

#### `sudo`
**Description:** Runs commands as the superuser.  
**Example:**
```bash
sudo apt-get update
```

---

### Network Management Commands

#### `ifconfig`
**Description:** Configures network interfaces.  
**Example:**
```bash
ifconfig eth0
```

#### `ping`
**Description:** Tests network connectivity.  
**Example:**
```bash
ping google.com
```

#### `netstat`
**Description:** Displays network connections, routing tables, etc.  
**Example:**
```bash
netstat -tuln
```

#### `ssh`
**Description:** Securely connects to remote systems.  
**Example:**
```bash
ssh user@hostname
```

#### `scp`
**Description:** Securely copies files between hosts.  
**Example:**
```bash
scp file.txt user@remotehost:/path
```

---

### Disk Management Commands

#### `df`
**Description:** Reports file system disk space usage.  
**Example:**
```bash
df -h
```

#### `du`
**Description:** Estimates file space usage.  
**Example:**
```bash
du -sh /home/user
```

#### `fdisk`
**Description:** Manipulates disk partition tables.  
**Example:**
```bash
fdisk -l
```

#### `mount`
**Description:** Mounts file systems.  
**Example:**
```bash
mount /dev/sda1 /mnt
```

#### `umount`
**Description:** Unmounts file systems.  
**Example:**
```bash
umount /mnt
```

---

### Package Management Commands

#### `apt-get`
**Description:** Manages packages on Debian-based systems.  
**Example:**
```bash
sudo apt-get install package
```

#### `yum`
**Description:** Manages packages on Red Hat-based systems.  
**Example:**
```bash
sudo yum install package
```

#### `dpkg`
**Description:** Manages Debian packages.  
**Example:**
```bash
dpkg -i package.deb
```

#### `rpm`
**Description:** Manages RPM packages.  
**Example:**
```bash
rpm -ivh package.rpm
```

#### `snap`
**Description:** Manages snap packages.  
**Example:**
```bash
sudo snap install package
```

---

### Text Processing Commands

#### `cat`
**Description:** Concatenates and displays file content.  
**Example:**
```bash
cat file.txt
```

#### `grep`
**Description:** Searches text using patterns.  
**Example:**
```bash
grep "pattern" file.txt
```

#### `awk`
**Description:** Processes and analyzes text files.  
**Example:**
```bash
awk '{print $1}' file.txt
```

#### `sed`
**Description:** Edits text in a scriptable manner.  
**Example:**
```bash
sed 's/old/new/g' file.txt
```

#### `sort`
**Description:** Sorts lines of text files.  
**Example:**
```bash
sort file.txt
```

---

**Author:** SAGAR SINHA

