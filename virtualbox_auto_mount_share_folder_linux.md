* title: How to configure a share folder with Linux Mint Guest
* url: https://forums.virtualbox.org/viewtopic.php?f=6&t=60226
* autor: Testing
* date:  20. Feb 2014, 04:44 

```
sudo mount -t vboxsf <ShareNmae> Desktop/VirtualBoxShare/
```

The next thing you probably want to do is mount the share automatically when you start Mint.

I originally tried to edit the fstab file, which is what it says in the VirtualBox documentation, but this didn't work:

```
sudo gedit /etc/fstab (or use nano)
```

Apparently fstab mounts the file system before vboxvfs has even been loaded. Luckily we can just put our mount command in the /etc/rc.local file:

Code: Select all   Expand view
```
        sudo gedit /etc/rc.local
```

Before the"exit 0" command add the mount line from above (you don't need sudo anymore as rc.local will be executed as a superuser.
