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
    














