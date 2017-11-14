---
title: "Linux install"
date: 2017-11-13
---

My old hard drive is broken and I bought a new SSD (Kingston A400 120G) and SSD mount. 

First I try to install Linux Mint following this (instruction)[https://forums.linuxmint.com/viewtopic.php?t=122276]. However, 
the (“The creation of swap space in partition #6 of SCSI2 (0,0,0) (sda) failed”)[https://askubuntu.com/questions/339677/how-can-i-fix-the-creation-of-swap-space-in-partition-6-of-scsi2-0-0-0-sda]
error happened. 

Then I copy the whole iso image from flash drive to the new SSD with

```shell
sudo dd if=/dev/sdb of=/dev/sda bs=1M
```
and install it from the SSD. The problem was not solved.

So I try to install Ubuntu. but the problem ("ubuntu grub-install /dev/sda failed")[https://askubuntu.com/questions/143678/i-receive-the-error-grub-install-dev-sda-failed-while-attempting-to-install-u]
appeared.

As I already partitioned the SSD and I wanted to reset the SSD to factory settings. I tried
```shell
sudo dd if=/dev/zero of=/dev/sda bs=1M
```

but canceled it.

Then I found this [article](https://unix.stackexchange.com/questions/289283/redefining-partitions-from-ubuntu-live-usb/289289),

```shell
dd if=/dev/zero of=/dev/sdb count=4 bs=1M
```
This will remove any filesystem signature at the start and then try 
```shell
fdisk /dev/sda 
```
and follow the instrction to create a new DOS partition table.

Also in the Disk Util App, I can delete other partitions.
