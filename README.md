<h1> Dview8 QA Tips </h1>


   
## ```Recommend Tools```

+ WSL
+ Wireshark
+ putty
+ tftp64




## ``` Tools cheatsheet ```

  + [WSL install reference](https://learn.microsoft.com/zh-tw/windows/wsl/install)
     
  +  WireShark
  ![](/.imgs/wireshark.gif)
     use ``` ip.addr==targetIP ``` to filter IP, add && means AND another parameter to filter packages, like sflow, tftp etc.  
  + putty
    <br> 
    I just use to connect console port.
    ![](/.imgs/serialport.gif)

    <font color=red>COM*</font> is your serial port

    ![](/.imgs/putty.gif)

    If you can't connect console with serial port, change baud rate 9600 => 115200
  + tftp64
    ![](/.imgs/tftp64.gif)

    <font color=red>Probe Must stop</font> or TFTP's 69 port got used tftp64 cannot launch !

    ``` Set a directory as server's files ```

    I create tftp dir on Desktop to save firmware then GUI choose tftp upgrade set your localIP and your file name.




## ``` QA Test Records ```

- [Verify the Templates](#verify-the-templates)
- [Device View](#device-view)
- [Panel](#panel)
- [Port\_Traffic](#port_traffic)
- [PrivatePortInfo](#privateportinfo)
- [BaseInfo](#baseinfo)
- [Device Common Info](#device-common-info)
- [CPU Utiliztion \& Memory Utilzation](#cpu-utiliztion--memory-utilzation)
- [Temperature](#temperature)
- [Fan(if supported)](#fanif-supported)
- [PowerStatus(if support)](#powerstatusif-support)
- [LACP](#lacp)
- [Stack](#stack)
- [DLMS(if support)](#dlmsif-support)
- [SNTP](#sntp)
- [DHCP](#dhcp)
- [Trap](#trap)
- [Syslog](#syslog)
- [STP](#stp)
- [LLDP](#lldp)
- [Safeguard Engine](#safeguard-engine)
- [RMON](#rmon)
- [SSH](#ssh)
- [Telnet](#telnet)
- [HTTP \& HTTPS](#http--https)
- [Backup](#backup)
- [Restore](#restore)
- [Firmware Upgrade](#firmware-upgrade)
- [Reboot](#reboot)
- [PoE](#poe)
- [sFlow](#sflow)
- [Save](#save)
# Verify the Templates
![](/.imgs/1.png)

1. Monitor Tamplate
   ![](/.imgs/2.png)
2. Configuration Tamplate
   ![](/.imgs/3.png)
3. Panel Tamplate
   ![](/.imgs/4.png)
4. Other(SOID, Model Name, Hardware Version etc.)
      ![](/.imgs/5.png)

# Device View
![](/.imgs/6.png)

![](/.imgs/7.png)

# Panel
![](/.imgs/8.png)

* <font color=#FF0000>Red Arrow</font> - Layout & Vendor Icon
* <font color=#8000a0>Purple</font> Arrow - Port Type

# Port_Traffic
![](/.imgs/9.png)
  - MIB Browser
   ![](/.imgs/10.png)

   Search <font color=aqua>interfaces</font> click it will see ifTable
   <br>
   Search <font color=ruby>ifMIB</font> click it then click ifMIBObjects will see ifXTable 
   ![](/.imgs/11.png)

# PrivatePortInfo
   <br>
   `` used to turn on loopback detection ``
   ![DV8](/.imgs/privateport_dv8.png)
   ![GUI](/.imgs/privateport_gui.png)


# BaseInfo
   ![](/.imgs/12.png)
   ![](/.imgs/13.png)

   These toast need to support read-write

# Device Common Info
   check MAC, Hardware, Firmware, Total Flash(if supported)
   ![](/.imgs/14.png)

   SN(Serial Number)

   ![Go to Device View](/.imgs/15.png)

   ![](/.imgs/16.png)

# CPU Utiliztion & Memory Utilzation
   ![from Device Detail](/.imgs/17.png)

   ![Go to Device View](/.imgs/15.png)
   
   ![from Device View](/.imgs/18.png)
   
   ![Go to Customized Dashboard](/.imgs/19.png)
   
   ![Add Dashboard](/.imgs/cpu.gif)
   
   ![Reports](/.imgs/reports.gif)

# Temperature
   ![from Device Detail & Device View](/.imgs/temp.gif)

   Customized Dashboard & Reports same as CPU & Memory

# Fan(if supported)
   ![from Device Detail](/.imgs/fan.gif)

# PowerStatus(if support)
 ```  refer to Fan > Device Detail Hardware Health ```  


# LACP
  ![GUI](/.imgs/lacp_gui.gif)

  ![DV8](/.imgs/lacp_dv8.gif)
# Stack
  ![](/.imgs/stack.gif)

  content: 
  + set priority ASC or DESC <font color='red' size=5 px>Base on device's manual</font> decide which device is master, others are slave, if priority same (like example) will base on MAC ADDRESS usually.
  + stacking port's linking method have two type, one is ring the other is chain
    - Chain
    ![](/.imgs/stacking_chain.png)

    - Ring
    ![](/.imgs/stacking_ring.png) 
# DLMS(if support)
  ![](/.imgs/dlms.gif)
# SNTP
   ![GUI](/.imgs/sntp_gui.gif)
   ![DV8](/.imgs/sntp_dv8.gif)
# DHCP
  ![](.imgs/dhcp_open.gif)
  ![](.imgs/dhcp_close.gif)
# Trap
  ![](/.imgs/trap.gif)
# Syslog
  ![](/.imgs/syslog.gif)
# STP
  ![](/.imgs/stp_open.gif)
  ![](/.imgs/stp_close.gif)
# LLDP
  ![](/.imgs/lldp.gif)
# Safeguard Engine
  ![](/.imgs/se.gif)
# RMON
  ![](/.imgs/rmon_open.gif)
  ![](/.imgs/rmon_close.gif)
# SSH
  ![](/.imgs/ssh_close.gif)
  
  ![](/.imgs/ssh_open.gif)
# Telnet
  ![](/.imgs/telnet_open.gif)
  
  ![](/.imgs/telnet_close.gif)
  
  ![](/.imgs/telnet_config_port.gif)
# HTTP & HTTPS
  ![](/.imgs/https_dv8.gif)
  
  ![](/.imgs/http%26https_port_isOpened.gif)
  
  ![](/.imgs/http_dv8.gif)
  
  ![](/.imgs/http_dv8_config_port.gif)
# Backup
  ![](/.imgs/backup.gif)
# Restore 
  <font color='#1da' size=5 px>refer to Backup and compare with it</font> 

  ![](/.imgs/restore1.gif)
  
  ![](/.imgs/restore2.gif)
  
# Firmware Upgrade
  ![](/.imgs/fwupgrade_upload.gif)
  
  ![](/.imgs/fwupgrade_reboot.gif)
  
  ![](/.imgs/fwupgrade_complete.gif)
# Reboot
  ![](/.imgs/reboot1.gif)
  
  ![](/.imgs/reboot2.gif)
# PoE
  ![](/.imgs/poe.gif)
- [ ] 802.1Q VLAN
# sFlow
  ![](/.imgs/sflow.gif)

  content: 
   * Collect Address is your Local IP, if device ip 192.168.110.*, <font color='red'>your need to change your Local IP</font> , for example is at 192.168.220.* 
   * ```(same logic on backup and restore, if you failed check IP first)```
   * Sampler Port fill which is Linked, Rate set Max(65536)
   * Counter Poller Interval means 1/*packages.
# Save
   ![](/.imgs/save.gif)

