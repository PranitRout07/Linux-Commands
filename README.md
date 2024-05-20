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

















