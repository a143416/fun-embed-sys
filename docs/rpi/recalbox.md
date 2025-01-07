```sh
ssh root@recalbox.local
pass: recallboxroot
```

## Issue 1
When Recalbox on a Raspberry Pi resets its controller configuration after each boot, it typically indicates an issue with how settings are saved. Here are the common causes and solutions:
1. File System Not Writable

Recalbox requires write access to its configuration files. If the file system is mounted as read-only, changes will not persist.

Solution: Ensure that the /recalbox/share partition (where settings are stored) is writable. Run this command via SSH or terminal:
```sh
mount | grep recalbox/share
```

If it shows read-only (ro), remount it as read-write:

```sh
mount -o remount,rw /recalbox/share
```

## Dashboard

Type this to browser: `http://recalbox.local/`


## Netwrok

```sh
nano /recalbox/share/system/recalbox.conf

wifi.enabled=1
wifi.ssid=YourNetworkSSID
wifi.key=YourNetworkPassword
```
## Check MD5
```sh
md5sum <filename>
```

## Check Devices on Network
```sh
sudo apt install nmap
sudo nmap -sn -PR 192.168.0.5/24
```
##
