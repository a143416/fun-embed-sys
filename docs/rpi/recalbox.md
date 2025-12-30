```sh
ssh root@recalbox.local
pass: recalboxroot
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

## Theme
https://wiki.recalbox.com/en/tutorials/frontend-customization/add-themes-into-emulationstation

## Controller First Setup

Quick Fixes (Try These First)

    Restart System: A simple reboot (via power cycle or reboot command via SSH) can resolve temporary glitches.
    HotKey Combo: Press HotKey + Start (often the "Select" button on your controller) to bring up the in-game menu or exit to the system menu.
    Keyboard: Connect a USB keyboard to navigate settings and remap your controller. 
    
If the Menu is Still Inaccessible (Controller Not Working at All)

    Reset Controller: For Bluetooth controllers, press the small reset button on the controller itself (often a tiny pinhole).
    Reconfigure in Settings:
        Navigate to Main Menu > Controller Settings (use keyboard if needed).
        Select "Configure a controller" and follow prompts to map buttons.
    Delete Config Files (Advanced):
        Connect via SSH or access files via network share (\\SHARE\system).
        Delete es_input.cfg (in \SHARE\system\.emulationstation) and DEFAULT.cfg (in \SHARE\system\configs\retroarch\inputs).
        Restart the system. 
```sh
nano configs/retroarch/inputs/DEFAULT.cfg
```
