
# Day 10 Challenge

## Files Created
[list files]
```
## file created
ubuntu@training:~/devops/day-10$ touch devops.txt
ubuntu@training:~/devops/day-10$ cat ~/devops/nginx-logs.txt > notes.txt
ubuntu@training:~/devops/day-10$ ls -tlr
total 4
-rw-rw-r-- 1 ubuntu ubuntu    0 Jun  2 15:53 devops.txt
-rw-rw-r-- 1 ubuntu ubuntu 3729 Jun  2 15:54 notes.txt
ubuntu@training:~/devops/day-10$ vim script.sh
ubuntu@training:~/devops/day-10$ ls -tlr
total 8
-rw-rw-r-- 1 ubuntu ubuntu    0 Jun  2 15:53 devops.txt
-rw-rw-r-- 1 ubuntu ubuntu 3729 Jun  2 15:54 notes.txt
-rw-rw-r-- 1 ubuntu ubuntu   38 Jun  2 15:55 script.sh


## reading file:

ubuntu@training:~/devops/day-10$ head /etc/passwd -n 5
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
ubuntu@training:~/devops/day-10$ tail /etc/passwd -n 5
vboxadd:x:997:1::/var/run/vboxadd:/bin/false
tokyo:x:1001:1001::/home/tokyo:/bin/sh
berlin:x:1002:1002::/home/berlin:/bin/sh
professor:x:1003:1003::/home/professor:/bin/sh
nairobi:x:1004:1006::/home/nairobi:/bin/sh

```

## Permission Changes
```

# Before:
ubuntu@training:~/devops/day-10$ ls -l
total 8
-rw-rw-r-- 1 ubuntu ubuntu    0 Jun  2 15:53 devops.txt
-rw-rw-r-- 1 ubuntu ubuntu 3729 Jun  2 15:54 notes.txt
-rw-rw-r-- 1 ubuntu ubuntu   38 Jun  2 15:55 script.sh


# After : 
buntu@training:~/devops/day-10$ ls -l
total 12
-r--r--r-- 1 ubuntu ubuntu    0 Jun  2 15:53 devops.txt
-rw-r----- 1 ubuntu ubuntu 3729 Jun  2 15:54 notes.txt
drwxr-xr-x 2 ubuntu ubuntu 4096 Jun  2 16:05 project
-rwxr--rw- 1 ubuntu ubuntu   38 Jun  2 15:55 script.sh

```

#error

```
ubuntu@training:~/devops/day-10$ echo "weclome" >> devops.txt 
bash: devops.txt: Permission denied

buntu@training:~/devops/day-10$ ./script.sh
bash: ./script.sh: Permission denied

```

## Commands Used

```
279  touch devops.txt
  280  cat ~/devops/nginx-logs.txt > notes.txt
  281  ls -tlr
  282  vim script.sh
  283  ls -tlr
  284  vim -r script.sh 
  285  vim -r script.sh
  286  view script.sh
  287  vim -R script.sh
  288  head /etc/passwd -n 5
  289  tail /etc/passwd -n 5
  290  ls -l
  291  chmod 746 script.sh 
  292  chmod 666 devops.txt 
  293  chmode 640 notes.txt 
  294  chmod 640 notes.txt 
  295  mkdir project
  296  chmod 755 project
  297  ls -l
  298  chmod 444 devops.txt 
  299  ls -l
  300  echo "weclome" >> devops.txt 
  301  chmod -x script.sh 
  302  ls -l
  303  ./script.sh
  304  history


```

## What I Learned
">" is used to redirect the output of cmd result into text file
after changing the premission also check if it is reflected correctly.
