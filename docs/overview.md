# Overview

cf site buildout generics

## Basic Stack

### Infra front
- [192.168.1.1](http://192.168.1.1) SOHO router PUBLIC-IP: 24.149.26.202 (has inbound blocks)
- [192.168.1.2](http://192.168.1.2) FreeNAS root-What#Time
- [192.168.1.3](http://192.168.1.3) GitLAB root-What#Time
- [192.168.1.4](http://192.168.1.4) nginx (was tobe the inbound web proxy config through freenas)
- [192.168.1.9](http://192.168.1.9) HPE BladeSystem Onboard Admin (use firefox) admin-What#Time

### Infra DHCP
- 192.168.1.20-199 DHCP via 192.168.1.1
- [192.168.1.72](http://192.168.1.72) Cisco Switch in HPE (DHCP) (use firefox)
- [192.168.1.40](http://192.168.1.40) ILO HPE (DHCP) (use firefox)
- [192.168.1.62](http://192.168.1.62) ILO HPE (DHCP) (use firefox)
- [192.168.1.72](http://192.168.1.72) Cisco Switch in HPE (DHCP) (use firefox)
- [192.168.1.142](http://192.168.1.142) Plex (DHCP)

### Infra back
- [192.168.1.201:8009](http://192.168.1.201:8009) ProxMox cf  (master node) root-What#Time
- [192.168.1.202:8009](http://192.168.1.202:8009) ProxMox cf2 (cluster node)


## Vitrual Machines
- cent7min on Proxmox
  - [192.168.1.201:8009](http://192.168.1.201:8009) ProxMox cf
  - cf->local(cf)->Upload->"CentOS-7-x86_64-Minimal-1810.iso"
  - Create VM (cent7min) - proxcatgrid Color#What!
    - Node: cf | VM ID: 100 | Name: cent7min | Pool: catgridPool
    - Boot: CD - Storge: local ISO image: CentOS-7-x86_64-Minimal-1810.iso
    - OS: Linux 4.x/3.x/2.6 Kernel
    - System: Graphic: Default SCSI Ctr: VirtIO SCSI
    - SCSI Controller: VirtIO | Bus: SCSI | Storage: local-lvm | Size: 9G
    - CPU: 2 | Memory: 1024
  - Create VM (bareMetal)
    - Node: cf | VM ID: 101 | Name: bareMetal | Pool: catgridPool
    - Boot: Do not use any media
    - OS: Linux 4.x/3.x/2.6 Kernel  
    - System: Graphic: Default SCSI Ctr: VirtIO SCSI
    - SCSI Controller: VirtIO | Bus: SCSI | Storage: local-lvm | Size: 6G
    - CPU: 1 | Memory: 512
    - Network Bridge: vmbr0 | Model: VirtIO
    
## VLAN for Testing pxe

- Go to [192.168.1.9](http://192.168.1.9) HPE BladeSystem Onboard Admin (use firefox) admin-What#Time
- Enclosure->Interconnect->CiscoSwtich->ManagementConsole
- should take you to [192.168.1.72](http://192.168.1.72) Cisco Switchroot

## Setup digital-rebar on cent7min

## Test PXE boot
 
## Reference docs

- [2cld-NetworkLayout](https://docs.google.com/spreadsheets/d/1fIs0hXZehy1KZmvjHQ6srktOA0otWPfx2Bo0VUg2oa4/edit?ts=5cd30e41#gid=0) via christrees@gmail.com
- [2cld-DataCenterLayout](https://docs.google.com/spreadsheets/d/1QBA9OzsOhxs5W3kwlhxLZCmulFgd5uHMqu2qgrbMdxE/edit#gid=0) via admin@2cld.net (me)
