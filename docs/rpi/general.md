# General Guides
This doc provides useful code snippets commonly used when setting up a Raspberry Pi.

## WLAN USB Adapter
This [link](https://elinux.org/RPi_USB_Wi-Fi_Adapters) provides a detailed guide to install different USB adapters.

I own a TP-Link `TL-WN723N v3` based on the Realtek `RTL8188EUS` chipset. No manual installation is needed with the latest Raspbian as long as the adapter is directly plugged into Raspberry with proper power supply. Therefore, don't connect the adapter via a powered USB hub!

## RPI Info
To get general RPI info:
```sh
# print the Linux version
$ uname -a

# find model number
$ cat /sys/firmware/devicetree/base/model

# or
$ cat /proc/cpuinfo
```

## Enable SSH and VNC
Open terminal and type:
```sh
$ sudo raspi-config
```
Go to `Interface Options –> P2 SSH, Enable SSH`.

## Find IP Address
To find RPI IP, try:
```sh
$ ifconfig
```