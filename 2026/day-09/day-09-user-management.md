# Day 9 challenge

### users & groups created
 - User: tokyo, berlin, professor, nairobi
 - Gropus : developers, admins, project-team

## Group Assignments
| user | Group |
|--------|---------|
| tokyo | developers, project-team |
| berlin | developers, admins |
| professor | admins |
| nairobi | project-team |

## Directories Created
```Bash

ubuntu@training:~$ ls -l /opt
total 12
drwxrwxr-x 2 root developers   4096 Jun  1 14:37 dev-project
drwxrwxr-x 2 root project-team 4096 Jun  1 15:35 team-workspace

## file created:
ubuntu@training:~$ ls -l /opt/dev-project/
total 0
-rw-rw-r-- 1 tokyo tokyo 0 Jun  1 14:37 file1.txt

ubuntu@training:~$ ls -l /opt/team-workspace/
total 0
-rw-rw-r-- 1 nairobi nairobi 0 Jun  1 15:35 file2.txt

## Command Used

sudo useradd -m tokyo
sudo useradd -m berlin
sudo useradd -m professor
cat /etc/passwd
ls /home
sudo groupadd developers
sudo groupadd admin
usermod -aG developers tokyo
sudo usermod -aG developers tokyo
tail /etc/passwd
tail /etc/group
sudo groupmod -n admins admin
tail /etc/group
usermod -aG developers,admins berlin
sudo usermod -aG developers,admins berlin
sudo usermod -aG admins professor
tail /etc/group
sudo passwd tokyo
sudo passwd berlin
sudo passwd professor
sudo mkdir /opt/dev-project
sudo chgrp developers /opt/dev-project
ls -ltr /opt/
chmod 775 /opt/dev-project
sudo chmod 775 /opt/dev-project
su tokyo
touch /opt/dev-project/file1.txt
sudo useradd -m nairobi
sudo groupadd project-team
tail /etc/group
usermod -aG project-team nairobi
sudo usermod -aG project-team nairobi
sudo usermod -aG project-team tokyo
mkdir /opt/team-workspace
sudo mkdir /opt/team-workspace
chgrp project-team /opt/team-workspace
sudo chgrp project-team /opt/team-workspace
ls -ltr /opt
sudo chmod 775 /opt/team-workspace
ls -ltr /opt/
sudo passwd nairobi
su nairobi
touch /opt/team-workspace/file2.txt
ls -ltr /opt/team-workspace/
groups tokyo
ls -ld /opt
history


```

what I learned:
- Sudo premision is requried to create user, group, change group, change premission in root directory.
- understand useradd, passwd, usermod, groupadd, groups, chgrp, chmod
