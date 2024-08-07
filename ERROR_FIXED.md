# Case :- 
I have installed docker on ubuntu on a particular user.By default docker can only be accessed through root access . But i want my user should get the access of docker . 
To do this i have to add my user to the docker group . By mistake i have used this below command where instead of appending the group , i have completely modified the groups attached with 
the user . 
```
sudo usermod -G docker <myuser>
```
Now problem is , my user don't have any sudo access and also i don't know any root password. It has created a major problem now .

# How I solved it?

1. Now i have restarted the machine, entered escape button to go into advanced options with recovery mode during the boot.
2. Then here i have select the root shell prompt.
3. By default filesystem is read only, i have changed to read/write:
   ```
   mount -o remount,rw /
   ```
4. Now added the myuser to the sudo group.
   ```
   usermod -aG sudo <my user>
   ```
5. Then reboot the system.
   ```
   reboot
   ```
   This solved the issue.
