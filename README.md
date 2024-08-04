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
27. Watch continuosly the cpu
```
watch -n 1 "top -bn1 | grep 'Cpu(s)'"

```
28. Watch continuosly the memory
```
watch -n 1 "free -m"

```

29. 
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
7. Add a user to root group
```
sudo usermod -aG root <username>

```
8. Verify group of a user .
```
groups <username>
```

# Networking Commands
1. Check data transfering properly or not .This checks two parts : whether your internet is working or not and the server side is serving properly or not .
```
ping <ip or domain name>
```
2. Shows the network statistics. For example you can see all the active connections .
```
netstat
```
3. All the network interfaces . For example if you have installed docker, then by default docker creates a isolated network . You can see this after using ifconfig. Here you can see ipv4 and ipv6 addresses of each interface.
```
ifconfig
```
4. Suppose you are searching youtube.com , it does not directly goes to request the youtube.com server . The request travels through various servers by hopping from server to another . The entire path is shown through traceroute .
```
traceroute <domain name>
```
5. Check your network latency .
```
tracepath <domain name>
```
6. Ping and tracepath at the same time.
```
mtr <domain name>
```
7. Shows whether the website is active or not . It gives all information like server address .
```
nslookup <domain name>
```
8. Check by connection on a particular port for a domain.
```
telnet <domain name> <port>
```
9. Show the current machine ip.
```
hostname
```
10. Edit hostname and add a custom ip and hostname mapping . Change it in the file /etc/hosts.
```
cd /etc/hosts
```
11. Shows all the ip adresses .
```
ip address
```
12. Shows all the wireless connections.
```
iwconfig
```
13. Same function as netstat command .
```
ss
```
14. Show where a particular website is hosted
```
dig <domain name>
```
15. Shows all the details of a particular domain name like fro  where you have bought it , on which date you have bought this domain name and who is the registar .
```
whois <domain name> 
```
16. Shows the MAC address.
```
arp
```
17. Shows which network interface are working .
```
ifplugstatus
```
18. Hit api endpoints .
```
curl -X GET <api-endpint> {This is get , other option like POST is also available}
```
But after running the above command you will see the output is in very format(not readable). To make it more readable you can install 'jq' . 
```
curl -X GET <api-endpint> | jq
```
19. Download anything from internet .
```
wget <link>
```
20. Continuously runs a command every two second.
```
watch <any command>
for example:
watch top
You can also control the number of seconds also.

watch -n <time> <command>
```
21.  Scan the domain name and it shows which ports are open .
```
nmap <domain name>
```
22. Shows all the routes .
```
route
```

# Password Management
1. Password management can be done by using `chase` command or by changing the file `/etc/login.def`
```
chase [-m minimum day] [-M maxdays] [-d last day] [-I inactive] [-E expiredate] [-w warndays] <username>
```
2. Show details of username and password.
```
grep <username> /etc/shadow
```
3. Now using /etc/login.def

```
Following fields you can modify:
1) PASS_MAX_DAYS
2) PASS_MIN_DAYS
3) PASS_MIN_LEN
4) PASS_WARN_AGE
```
