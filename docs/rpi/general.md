# General Guides
This doc provides useful code snippets commonly used when setting up a Raspberry Pi.

## WLAN USB Adapter
This [link](https://elinux.org/RPi_USB_Wi-Fi_Adapters) provides a detailed guide to install different USB adapters.

I own a TP-Link `TL-WN723N v3` based on the Realtek `RTL8188EUS` chipset. No manual installation is needed with the latest Raspbian as long as the adapter is directly plugged into Raspberry with proper power supply. Therefore, don't connect the adapter via a powered USB hub!

## Model Info
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
To find the IP address of a Raspberry Pi connected to your router, you can try the following methods:

1. Router's Admin Page:

- Log in to your router's web interface. This usually involves entering the router's IP address (commonly something like `192.168.1.1` or `192.168.0.1`) into a web browser.
- Navigate to the section that lists connected devices. This might be under a menu labeled "Attached Devices," "Device List," "DHCP Clients," or something similar.
- Look for entries that match your Raspberry Pi. It might be listed by its hostname (often "raspberrypi" by default) or by its MAC address.

2. Using a Network Scanner:

- Use a network scanning tool like `nmap` or a mobile app like Fing to scan your network for connected devices.
- For `nmap`, you can run a command like `nmap -sn 192.168.1.0/24` (replace `192.168.1.0/24` with your network's IP range) from a computer on the same network.

3. Command Line on Another Device:

- If you have access to another computer on the same network, you can use the `arp-scan` command (Linux) or `arp -a` (Windows) to list devices on the network and identify the Raspberry Pi by its MAC address or hostname.

4. Directly on the Raspberry Pi:

- If you have a monitor and keyboard connected to the Raspberry Pi, you can use the terminal to find the IP address:
  - Open a terminal and type `hostname -I` or `ifconfig` (or `ip addr` for more detailed information).
  - This will display the IP address assigned to your Raspberry Pi.

5. Using Avahi (Bonjour) Service:

- If Avahi (Bonjour) is enabled on your Raspberry Pi, you can try accessing it using its hostname followed by `.local`. For example, `ping raspberrypi.local` from another device on the network.
