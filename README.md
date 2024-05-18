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
















