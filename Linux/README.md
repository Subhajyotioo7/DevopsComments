# 🐧 Linux Commands Cheat Sheet

> Professional GitHub-ready README based on the uploaded **Linux Short Notes for DevOps Engineers** PDF.

## 📚 Table of Contents

- Introduction
- Linux File System
- Basic Commands
- File & Directory Management
- User Management
- Group Management
- Linux Permissions
- ACL (Access Control List)
- Grep
- Find
- wc
- head & tail
- tar
- Job Automation
- sudo
- Networking

---

# Introduction

Linux is a free and open-source operating system created by **Linus Torvalds** in 1991.

---

# Linux File System

| Directory | Purpose |
|-----------|---------|
| `/` | Root |
| `/root` | Root user's home |
| `/home` | User home directories |
| `/bin` | User binaries |
| `/sbin` | System binaries |
| `/etc` | Configuration files |
| `/usr` | User applications |
| `/var` | Variable data & logs |
| `/tmp` | Temporary files |
| `/boot` | Boot files |
| `/dev` | Device files |
| `/media` | Removable media |
| `/mnt` | Mount point |
| `/opt` | Optional software |

---

# Basic Commands

## Current directory

```bash
pwd
```

Displays the current working directory.

## List files

```bash
ls
ls -l
ls -la
```

Lists files and directories.

## Change directory

```bash
cd
cd ..
cd ~
cd /
```

Navigate between directories.

## Kernel Information

```bash
uname
uname -r
uname -a
```

Shows Linux kernel information.

## Current User

```bash
whoami
```

Displays logged-in user.

## Date

```bash
date
```

Shows current date and time.

## History

```bash
history
```

Displays command history.

## Clear terminal

```bash
clear
```

---

# File & Directory Management

## Create directory

```bash
mkdir devops
mkdir dev qa test
mkdir -p dev/qa/test
mkdir student{1..10}
```

## Create files

```bash
touch notes.txt
touch file1 file2 file3
touch book{1..10}.txt
```

## Copy

```bash
cp source destination
cp -rvf project backup/
```

## Move / Rename

```bash
mv old.txt new.txt
mv file.txt /home/user/
```

## Delete

```bash
rm file.txt
rm -rvf folder
```

---

# User Management

```bash
useradd john
passwd john
su john
exit
userdel john
grep john /etc/passwd
```

---

# Group Management

```bash
groupadd developers
groupdel developers
gpasswd -a john developers
gpasswd -d john developers
grep developers /etc/group
```

---

# Linux Permissions

Check permissions

```bash
ls -l
```

Change permissions

```bash
chmod u+r file.txt
chmod g+rw file.txt
chmod o-r file.txt
chmod 755 project
```

Ownership

```bash
chown user file.txt
chgrp developers file.txt
```

Permission values

| Number | Meaning |
|--------|---------|
|7|rwx|
|6|rw-|
|5|r-x|
|4|r--|

---

# ACL

```bash
getfacl project
setfacl -m u:john:rwx project
setfacl -x u:john project
setfacl -b project
```

---

# Grep

```bash
grep root /etc/passwd
grep -i root /etc/passwd
grep -r root /
grep -n root /etc/passwd
grep -v root /etc/passwd
```

---

# Find

```bash
find /home -name "*.txt"
find / -user root
find / -group developers
find /tmp -size +10M
find /tmp -size -10M
```

---

# Word Count

```bash
wc -l file.txt
wc -w file.txt
wc -m file.txt
```

---

# Head & Tail

```bash
head file.txt
head -20 file.txt
tail file.txt
tail -f /var/log/messages
```

---

# Tar

```bash
tar -cvf backup.tar folder
tar -xvf backup.tar
tar -czvf backup.tar.gz folder
tar -xzvf backup.tar.gz
tar -cjvf backup.tar.bz2 folder
tar -cJvf backup.tar.xz folder
```

---

# Job Automation

```bash
at 8:00 AM
atq
atrm 1

crontab -e
crontab -l
crontab -r
```

Cron format

```text
* * * * * command
│ │ │ │ └── Day of Week
│ │ │ └──── Month
│ │ └────── Day
│ └──────── Hour
└────────── Minute
```

---

# Sudo

```bash
sudo command
visudo
usermod -aG wheel john
```

---

# Networking

```bash
ip addr
ifconfig
nmcli con show
nmcli con show --active
nmcli dev status
hostnamectl set-hostname devops-server
systemctl restart NetworkManager
```

---

# References

- Linux Manual (`man`)
- GNU Core Utilities
- Red Hat Documentation

---

⭐ Happy Learning!
