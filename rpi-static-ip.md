layout: page
title: "How to assign static IP address to Raspberry Pi"
permalink: https://letsstartlooping.github.io/TheForLoop/rpi-static-ip.md


# How to assign static IP address to Raspberry Pi?



Open the terminal and type following command. This will open the file that contains configuration information for *dhcpd*

```shell
sudo nano /etc/dhcpcd.conf
```

Scroll down to the very end of the file and type following for setting up static IP address for ethernet port

```bash
interface eth0
static ip_address=192.168.1.211/24
static routers=192.168.1.1
static domain_name_servers=192.168.1.1
```

Similarly type following for setting up static IP for Wi-fi

```bash
interface wlan0
static ip_address=192.168.1.210/24
static routers=192.168.1.1
static domain_name_servers=192.168.1.1
```

Only difference here is first line starting with word `interface`

`eth0`: Used for LAN

`wlan0`: Used for Wireless Network

Custom UP address should be added on 2nd line just before `/24`

