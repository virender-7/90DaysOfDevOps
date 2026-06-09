# Day 07 - linux File System Hierarchy & Scenario-Based practice


**Linux File System Hierarchy**

- / : Base of file system, only root user can write here
- /root : Root user's home directories. (Snap folder)
- /bin : Essential user command like ls, cp, grep available to all user, even in single-user mode.
- /sbin : System administration binaries such as iptales, fdisk, reboot, typically requring root privileges
- /boot – Bootloader files, kernel images (vmlinuz), and initrd files needed to start the system.
- /dev – Device files representing hardware (e.g., /dev/sda1 for a disk partition, /dev/tty for terminals).
- /etc – System-wide configuration files and startup scripts (/etc/passwd, /etc/resolv.conf).
- /home – Personal directories for non-root users (user folder e.g ubuntu)).
- /lib – Shared libraries required by binaries in /bin and /sbin.
- /media – Auto-mount points for removable media like USB drives or CDs.
- /mnt – Temporary mount point for manually mounted filesystems.
- /opt – Optional third-party software packages.
- /proc – Virtual filesystem with runtime system and process information (/proc/cpuinfo, /proc/meminfo).
- /srv – Data for services like web or FTP servers.
- /tmp – Temporary files, cleared on reboot.
- /usr – Secondary hierarchy for user applications, libraries, and documentation: 
    - /usr/bin – user commands. 
    - /usr/sbin – for administrator commands 
    - /usr/lib – Libraries for /usr/bin and /usr/sbin. 
    - /usr/local – Locally installed software.
- /var – Variable data like logs (/var/log), caches, and spool files.

**Hands-on task:**

#### largest log file
> du -sh /var/log/* 2>/dev/null | sort -h | tail -5
```

ubuntu@Ubuntu:/$ sudo du -sh /var/log/* 2>/dev/null | sort -h | tail -5
260K	/var/log/kern.log
888K	/var/log/dpkg.log
1.2M	/var/log/syslog
1.3M	/var/log/installer
41M	/var/log/journal

```

##### look at a config file in /etc
> cat /etc/hostname

ubuntu

#### check your home directory
> ls -la ~


**Scenario-Based Practice**

**Example Scenario: Check if a service is running**

- "nginx" service

- *step 1:* service status :$ systemctl status nginx

o/p: service is active
- *step 2:* if service is not found, list all services
 $ systemctl list-units --type=service 

- *step 3:* if service is enabled on boot
$ systemctl is-enabled nginx


**Scenario 2: High CPU Usage** 

- *step-1*: top or
    ps aux --sort=%cpu | head -10

**Scenario 3: finding service log**
journalct -u nginx -f (current process logs)

- tail -n 10 /var/log/nginx/access.log -f (current webapp response status)

**Scenario 4: File Premissions issue**

- ls -ltr <filename e.g backup.sh>
to check execute permission is (eg. -rw-r--r-- to added executable permision fr owner)

chmod 744 backup.sh
