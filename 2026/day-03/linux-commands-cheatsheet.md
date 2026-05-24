# Day 03 - Linux Commamds Practice

**Linux Command Cheat Sheet **
| Command | Description |
|-----------|---------------------------|
|**uname -r**| checks the version of the linux kernel your are running |
| **ps** | display information about the currently running processes |
| **ps -ef \| grep "process name"** | Search for a Specific Process |
| **top** | information about running processes, CPU usage, memory utilization, and system load averages |
| **htop** | enhanced version of top, more user friendly |
| **pwd** |  Prints the present working directory |
| **ls** | List files and directory in current folder |
| **cd** | change the directory  (cd .. : onelevel up) (cd ~ : home dir) |
| **mkdir** | creat a new dir |
| **touch** | create an empty file |
| **cp** | copies files or dir |
| **mv** | move or rename files |
| **rm** | remove files (rm -r : del a dir and its contents)
| **rmdir** | delete empty directories only |
| **cat** | Displays the full content of a files in terminal | 
| **find** | searched for files within a directory hierarchy |
| **file** | determines the file type (e.g .text, executable, or data) |
| **df -h** | shows availiable and used disk space |
| **du -sh** | display the size of a specifice dir or file (du -h| sort -h) |
| **chmod** | change file or directory premissions |
| **chown** | change the owner and group of a file | 
| **ping** | verfiy connectivity to another host or server | 
| **nslookup** | show the DNS server used. the queried domian and its IP add |
| **netstat -r** | inspect how network packets are routed |
|**netstat -tuln**| show all listening network ports on your stystm|
| **traceroute** | it help identify exactly which point in the network is causing a delay or drop |
| **ip addr** | (replacment for ifconfig) it display all network interfaces their status|
| **nmcli** | used on system with networkManager to view devie status and connection profiles |
| **dig** |  for querying DNS records,it provide detailed information about how a domain is being resolved.
| **curl** | used to transfer data to or from a server using various network protocols, including HTTP, HTTPS, FTP |
|**stat** | if checked for filename, provide the moredetail UID and GID |
|**free -h**|display temparory memeory available(RAM)|
|**watch <cmd>** | the default behaviouris to run the command every 2 seconds and display the output.

---------------------------------
**/etc