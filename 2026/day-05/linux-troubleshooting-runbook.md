# Day 05 – Linux Troubleshooting Drill: CPU, Memory, and Logs

## Task

- Target service / process 
> Nginx process and firefox

  - **Environment basics (2):** `uname -a`, `lsb_release -a` (or `cat /etc/os-release`)  
  - **Filesystem sanity (2):** create a throwaway folder and file, e.g., `mkdir /tmp/runbook-demo`, `cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo`  
  - **CPU / Memory (2):** `top`/`htop`/`ps -o pid,pcpu,pmem,comm -p <pid>`, `free -h`, `vm_stat` (mac)  
  - **Disk / IO (2):** `df -h`, `du -sh /var/log`, `iostat`/`vmstat`/`dstat`  
  - **Network (2):** `ss -tulpn`/`netstat -tulpn`, `curl -I <service-endpoint>`/`ping`  
  - **Logs (2):** `journalctl -u <service> -n 50`, `tail -n 50 /var/log/<file>.log`

- Snapshot: CPU & Memory
> **top** : "CPU 0.5 % and memory used 1786 outof 3582
> ps -ef | grep ngnix : 
    run by user(root), display pid 
> ps aux --sort=%mem | grep ngnix
   → Worker process, using 1.7% of RAM, 0.3% CPU, owned by www-data, stat sleeping.
   → Master process, using 0.5% of RAM, almost no CPU, owned by root, stat sleeping.
      - table details:
      | Colum |	Meaning |
      | USER |	  The account running the process (root, www-data, etc.) |
      | PID |	  Process ID — unique number for the process
      | %CPU |	  CPU usage (average since process start)
      | %MEM |	  Percentage of physical RAM used |
      | VSZ	|    Virtual memory size in KiB |
      | RSS	|    Resident Set Size — actual RAM in KiB |
      | TTY |	    Terminal controlling the process (? means none) |
      | STAT	|  Process state (S = sleeping, R = running, Z = zombie, plus flags like s, l, +) |
      | START |	  Time/date process started |
      | TIME |	  Total CPU time consumed |
      | COMMAND |	Command and arguments used to start the process |
> free -h : free memory around 30% VSZ is 14048 

- Snapshot: Disk & IO
> df -h : filesystem space for /dev/sda2 out of 25gb only 6.7gb is used and 17 g is available
> du -sh /var/log : 79M space consumed.

- Snapshot: Network
> ss -tulpn/nestat -tulpn: all the tcp and udp porto with listening ports with stat as LISTEN and UNCONN
> curl -I http://localhost
    - http resposnse as 200 with detail like server, date, content-type, content-length, connection
> ping : to check the service-endpoint is connect or not.

- Logs reviewed
  > tail -n 20 /var/log/nginx/access.log : observed 304 response for mozilla bowser and 200 respponse for curl cmd
  > tail -n 20 /var/log/nginx/error.log :  observed error e.g. using inherited sockets from "5:6" at timestamp 05:08:14 2026/05/24
  > jorunalctl -u nginx - n 50 : provided the niginx.service starting and stopping, stopped details with current state 
- Quick findings
  > Nignix process was not causing any
  > fierfox consumed more momery
- If this worsens (next steps)
  > check log file of service which are causing more memory.
  > restarting of service, which may cause the connection issue.
