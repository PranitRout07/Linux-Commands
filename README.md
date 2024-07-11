# Linux-Commands

1. Find number of CPUs on the server . (here 3 methods)
```
cat /proc/cpuinfo | grep -i proc | wc -l
```
```
nproc
```
```
lscpu
```

2. CPU Speed in megahertz(mhz)

```
cat /proc/cpuinfo | grep -i MHZ
```
3. Any information related to memory

```
cat /proc/meminfo
```

4. All the system details

```
uname -a
```

5. Current User

```
whoami
```

6. See free and used memory

```
free -h
```

7. Display and manage the top processes

```
top
```


8. Increase CPU load

```
while true; do uptime; sleep 2; done
```

9. To see the background jobs running

 ```
 jobs
 ```
10. Kill a background job

```
sudo kill <pid>
```
11. See all the processes running

```
ps -ef
```

12. Change user permission

```
chown
```

13. Heavy task to increase cpu stats 
```
for i $(seq 1 100000000000000); do print $i; done 
```
14. Heavy compress 
```
dd if=/dev/urandom of=/dev/null bs=1024k count=10000 
```
15. Add a user

```
sudo useradd 
```

16. Remove caches (carefuly use this command as sometimes some systems need cache to run correctly )
```
echo 3 > /proc/sys/vm/drop_caches
```
17. Generate high memory loads .(use the command 

```
stress m -6
```
18. All used space in /Root partition
```
df -h
```
19. All the processes running inside the current directory .

```
lsof .
```

20.Long listing of /root , /tmp , /etc/shadow ,etc/password , /etc/ssh/ssh_config
```
ls -ld /root /tmp /etc/shadow /etc/passwd /etc/ssh/ssh_config
```
    
21. Number of disks

```
sudo fdisk -l
```
22. Check number of disk partitions
```
sudo fdisk -l | grep -i sd
```

```
lsblk
```
23. Check file system on the partitions

```
lsblk -f
```

24. Check partitions not mounted for filesystem types

```
mount | wc -l
```


25. All system details .
Here you can install neofetch then use the command to see the system details .
```
sudo apt install neofetch
```
After installation run this 
```
neofetch
```
26. Do math operation in terminal .

```
sudo apt install bc
```
Now write like this to do math operation 
```
echo "78*89" | bc
```
# User Account Management

1. Add a user
```
useradd -g <group-name> -s /bin/bash -c <"description"> -m -d /home/<username> <username>
```
2. Check whether user is created or not.
```
id <username>
```
3. Delete a user
```
userdel <username>
```
4. Modify a user.
```
usermod -G <group-name> <username>
```
Change the default group name
```
usermod -g <group-name> <username> 
```
```
Other flags we can use for modification are
-m -d <new-directory>
-p <new-password>
-s <shell-type>
-L <lock>
-U <unlock>
```
5. Create a group
```
groupadd <group-name>
```
6. Delete group
```
groupdel <group-name>
```








