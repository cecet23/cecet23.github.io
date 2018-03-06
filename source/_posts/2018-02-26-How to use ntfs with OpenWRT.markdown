---
title: How to use an ntfs' HD on openwrt
date: 2018-02-26 12:07:24 Z
categories:
- Openwrt
layout: post
---

First of all you have to use usb's driver. Personally I installed uhci and ohci's drivers.

modules for USB 1.1:

```
opkg update
opkg install kmod-usb-uhci
opkg install kmod-usb-ohci
```

then for usb 2:

```
opkg install kmod-usb2
```

You need to install the usb storage's module.

```
opkg install kmod-usb-storage kmod-usb-storage-extras
```

At least you have to install ntfs-3g package and mount the HD:

```
opkg install ntfs-3g
mkdir /mnt/usb-ntfs
ntfs-3g /dev/sda1 /mnt/usb-ntfs -o rw,sync
```

if everything went fine you can find your HD on /mnt/usb-ntfs.

Some other usefull cmd:


```
df -h
```


```
dmesg | grep sd
```

to see if the usb's driver are load:
```
cat /sys/kernel/debug/usb/devices
```

and you will see something like that:
```
T:  Bus=03 Lev=01 Prnt=01 Port=01 Cnt=01 Dev#=  2 Spd=5000 MxCh= 0
D:  Ver= 3.00 Cls=00(>ifc ) Sub=00 Prot=00 MxPS= 9 #Cfgs=  1
P:  Vendor=0480 ProdID=a200 Rev= 0.00
S:  Manufacturer=TOSHIBA
S:  Product=External USB 3.0
S:  SerialNumber=20150207004253C
C:* #Ifs= 1 Cfg#= 1 Atr=80 MxPwr=896mA
I:* If#= 0 Alt= 0 #EPs= 2 Cls=08(stor.) Sub=06 Prot=50 Driver=usb-storage
E:  Ad=81(I) Atr=02(Bulk) MxPS=1024 Ivl=0ms
E:  Ad=02(O) Atr=02(Bulk) MxPS=1024 Ivl=0ms
```


