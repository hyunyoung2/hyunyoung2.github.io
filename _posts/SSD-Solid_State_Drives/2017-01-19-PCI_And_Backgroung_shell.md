---
layout: post
title: How to program to EEPROM and What is writing to EEPROM ? 
subtitle: Summary about Writing to EEPROM consists of nor-gate and Background shell programming
category: SSD (Solid State Drives)
tags: [nvme, EEPROM]
permalink: /2017/01/19/PCI_And_Backgroung_shell/
---

# Change of the number of PCI

if a carrier card has four NVMe SSD, But the number of PCI slot on a carrier card is more one than what PCI switch perceives. 

So, I couldn't boot OS, and I could'nt even enter BIOS state. then What is the solution of this problem. 

That is to reduce the number of PCI slot on a carrier card. 

If the number of PCI slot is wrong like this. 


## the number of PCI slot is more one than what PCI switch perceives. 

```shell 
$ lspci -tv
-[0000:00]-+-00.0  Intel Corporation 
           .......
           +-1c.0-[01]--
           +-1c.3-[02-03]----00.0-[03]--
           +-1c.4-[04-0a]----00.0-[05-0a]--+-01.0-[06]----00.0  Device SSD
           |                               +-02.0-[07]----00.0  Device SSD
           |                               +-08.0-[08]--
           |                               +-09.0-[09]----00.0  Device SSD
           |                               \-0a.0-[0a]----00.0  Device SSD
           +-1d.0  Intel Corporation 
           .....       
 ```
 
 As you can see even though devices is four on a card, PCI slot is five. 
 
 I have to reduce this PCI slot Writing to the EEPROM with binary file. 
 
 That binary file is to reduce one of PCI slots like this.
 
 ```shell
 $ lspci -tv
-[0000:00]-+-00.0  Intel Corporation 
           .........
           +-1c.0-[01]--
           +-1c.3-[02-03]----00.0-[03]--
           +-1c.4-[04-0a]--+-[0000:0a]---00.0  Device SSD
           |               +-[0000:09]---00.0  Device SSD
           |               +-[0000:07]---00.0  Device SSD
           |               +-[0000:06]---00.0  Device SSD
           |               +-[0000:05]-+-01.0  PLX Technology, Inc. Device SSD
           |               |           +-02.0  PLX Technology, Inc. Device SSD
           |               |           +-08.0  PLX Technology, Inc. Device SSD
           |               |           +-09.0  PLX Technology, Inc. Device SSD
           |               |           \-0a.0  PLX Technology, Inc. Device SSD
           |               \-[0000:04]---00.0  PLX Technology, Inc. Device SSD
           +-1d.0  Intel Corporation 
           ........
 ```
 
 let's another An examle
 
 this change is implement with only PCI board without SSD 
 
 ```shell
 $ lspci -tv
-[0000:00]-+-00.0  Intel Corporation 
           ..........
           +-1c.0-[01]--
           +-1c.3-[02-03]----00.0-[03]--
           +-1c.4-[04-0a]----00.0-[05-0a]--+-01.0-[06]--
           |                               +-02.0-[07]--
           |                               +-08.0-[08]--
           |                               +-09.0-[09]--
           |                               \-0a.0-[0a]--
           ...........
           
after writting to the EEPROM with file(binary file), the follwoing

$ lspci -tv
-[0000:00]-+-00.0  Intel Corporation 
           ..........
           +-1c.0-[01]--
           +-1c.3-[02-03]----00.0-[03]--
           +-1c.4-[04-09]----00.0-[05-09]--+-01.0-[06]--
           |                               +-02.0-[07]--
           |                               +-09.0-[08]--
           |                               \-0a.0-[09]--
           +-1d.0  Intel Corporation 
           ..........
 ````
 
 since the number of PCI slots is reduced, I could reboot OS
 
 I used  GUI tooo on windows(PLX)to change the number of PCI slot.
 
<!--
 
 [PLX PEX Device editor](https://www.broadcom.com/products/pcie-switches-bridges/software-dev-kit)
 
 Aardvark tool -- Aardvark I2C/SPI Host Adapter, Sniffer, Exerciser, Memory & Flash Programmer
 
--> 
 
## BackGround shell 

if you want to execute shell's mutiple commands together, use **&**


```shell
[root@hyunyoung.lee ~]# for i in `seq 0 15`; do (nvme format /dev/nvme${i}n1 &); done
[root@hyunyoung.lee ~]# Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
Success formatting namespace:0
```

As you can see the above result, you can check those 15 process of command executed together.

don't forget **&**
