# DAY 12 Breather

- **Process & Service**: 
    ```Bash
    $ top
    $ ps -ef | grep nginx
    $ systemctl status ngnix
    ```
    - this cmd help in idenfity the current process and service which consuming more CPU and    service status.


- **Fileskills**
    ```BASH

    $ tail -10 /etc/passwd
    $ tail -10 /etc/group
    $ sudo chown tokyo:developers nginx-logs.txt
    ```
    - this cmd used to check recent user and group added and change owner and group of particular file

- **Cheat sheet refresh**
    ```BASH
    ps aux --sort=-%cpu | head -10
    ls -lt
    df -h
    find /etc/ -maxdepth 1 -type d -name 'ng*'
    ls -lt /var/log/nginx
    ```

- **User/group sanity**
    ```BASH
    sudo useradd -m golem
    sudo groupadd tester
    sudo usermod -aG tester golem
    sudo chown golem:tester team-notes.txt
    ```

