# View ownership
ls -l filename

Format: `-rw-r--r-- 1 owner group size date filename`
```Bash

ubuntu@training:~/devops$ ls -l nginx-logs.txt
-rw-rw-r-- 1 ubuntu ubuntu 3729 May 31 16:01 nginx-logs.txt

```
---

# Change owner only

```Bash

# Onwer details after creating file:
ubuntu@training:~/devops/day-11$ ls -tlr
total 0
-rw-rw-r-- 1 ubuntu ubuntu 0 Jun  3 13:08 devops-file.txt

#chown to tokyo
ubuntu@training:~/devops/day-11$ ls -tlr
total 0
-rw-rw-r-- 1 tokyo ubuntu 0 Jun  3 13:08 devops-file.txt

#chown to berlin
ubuntu@training:~/devops/day-11$ ls -ltr
total 0
-rw-rw-r-- 1 berlin ubuntu 0 Jun  3 13:08 devops-file.txt

```


# Change group only

```Bash

buntu@training:~/devops/day-11$ ls -l
total 0
-rw-rw-r-- 1 berlin ubuntu 0 Jun  3 13:08 devops-file.txt
-rw-rw-r-- 1 ubuntu ubuntu 0 Jun  3 13:22 team-notes.txt

ubuntu@training:~/devops/day-11$ ls -l
total 0
-rw-rw-r-- 1 berlin ubuntu     0 Jun  3 13:08 devops-file.txt
-rw-rw-r-- 1 ubuntu heist-team 0 Jun  3 13:22 team-notes.txt


```

# Change both owner and group
sudo chown owner:group project-config.yaml

```

ubuntu@training:~/devops/day-11$ ls -l
total 0
-rw-rw-r-- 1 berlin ubuntu     0 Jun  3 13:08 devops-file.txt
-rw-rw-r-- 1 ubuntu ubuntu     0 Jun  3 13:39 project-config.yaml
-rw-rw-r-- 1 ubuntu heist-team 0 Jun  3 13:22 team-notes.txt
ubuntu@training:~/devops/day-11$ ls -l project-config.yaml 
-rw-rw-r-- 1 ubuntu ubuntu 0 Jun  3 13:39 project-config.yaml
ubuntu@training:~/devops/day-11$ sudo chown professor:heist-team project-config.yaml
ubuntu@training:~/devops/day-11$ ls -l
total 0
-rw-rw-r-- 1 berlin    ubuntu     0 Jun  3 13:08 devops-file.txt
-rw-rw-r-- 1 professor heist-team 0 Jun  3 13:39 project-config.yaml
-rw-rw-r-- 1 ubuntu    heist-team 0 Jun  3 13:22 team-notes.txt

```

# Recursive change (directories)
sudo chown -R owner:group directory

```
ubuntu@training:~/devops/day-11$ ls -l heist-project/
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Jun  3 14:05 plans
drwxrwxr-x 2 ubuntu ubuntu 4096 Jun  3 14:05 vault
ubuntu@training:~/devops/day-11$ sudo chown -R  professor:planners ./heist-project/
ubuntu@training:~/devops/day-11$ ls -l heist-project/
total 8
drwxrwxr-x 2 professor planners 4096 Jun  3 14:05 plans
drwxrwxr-x 2 professor planners 4096 Jun  3 14:05 vault

ubuntu@training:~/devops/day-11$ ls -lR heist-project/
heist-project/:
total 8
drwxrwxr-x 2 professor planners 4096 Jun  3 14:05 plans
drwxrwxr-x 2 professor planners 4096 Jun  3 14:05 vault

heist-project/plans:
total 0
-rw-rw-r-- 1 professor planners 0 Jun  3 14:05 strategy.conf

heist-project/vault:
total 0
-rw-rw-r-- 1 professor planners 0 Jun  3 14:05 gold.txt

```



# Change only group with chown
sudo chown :groupname filename

```bash

ubuntu@training:~/devops/day-11$ sudo chown tokyo:vault-team bank-heist/access-code.txt 
ubuntu@training:~/devops/day-11$ sudo chown berlin:tech-team bank-heist/blueprints.pdf 
ubuntu@training:~/devops/day-11$ sudo chown nairobi:vault-team bank-heist/escape-plan.txt 
ubuntu@training:~/devops/day-11$ ls -l bank-heist/
total 0
-rw-rw-r-- 1 tokyo   vault-team 0 Jun  3 14:17 access-code.txt
-rw-rw-r-- 1 berlin  tech-team  0 Jun  3 14:18 blueprints.pdf
-rw-rw-r-- 1 nairobi vault-team 0 Jun  3 14:20 escape-plan.txt
ubuntu@training:~/devops/day-11$ 


```
