# Overview

cf site buildout generics

## Basic Stack

### Infra front
- [192.168.1.1](http://192.168.1.1) SOHO router PUBLIC-IP: 24.149.26.202 (has inbound blocks)
- [freenas.2cld.net - 00:15:17:5B:F3:78 - 192.168.1.2](http://192.168.1.2) catfreenas - FreeNAS root-What#Time
- [ gitlab.2cld.net - 00:15:17:B1:CF:59 - 192.168.1.3](http://gitlab.2cld.net) GitLAB root-What#Time (via DHCP)
- [     cf.2cld.net - 00:15:17:EE:CF:D6 - 192.168.1.9](http://192.168.1.9) nginx proxy


### Infra DHCP
- 192.168.1.20-40 DHCP via 192.168.1.1
 - [ghR4U23-OA1 - 00:1A:4B:CD:01:95	- 192.168.9.21]() HPE Onboard Admin		Administrator-What#Time
- [192.168.1.72](http://192.168.1.72) Cisco Switch in HPE (DHCP) (use firefox)
- [192.168.1.40](http://192.168.1.40) ILO HPE (DHCP) (use firefox)
- [192.168.1.62](http://192.168.1.62) ILO HPE (DHCP) (use firefox)
- [192.168.1.72](http://192.168.1.72) Cisco Switch in HPE (DHCP) (use firefox)
- [192.168.1.142](http://192.168.1.142) Plex (DHCP)

### Infra back
- [192.168.1.200](192.168.1.200) Win2016 - HyperV  Administrator-Color#What!
- [192.168.1.221:8009](https://192.168.1.221:8009) ProxMox pm1  (master node) root-Color#What!
- [192.168.1.222:8009](https://192.168.1.222:8009) ProxMox pm2 (cluster node)

## FreeBSD Gateway Router
- Look at the routes: netstat -rn
- Delete the bad: route del default
- Add default route: route add default 192.168.1.1
- Add default route: vi /etc/rc.conf: defaultrouter="192.168.1.1"
- Enable NAT: vi /etc/rc.conf: gateway_enable="YES"
- Restart networking: /etc/rc.d/netif restart && /etc/rc.d/routing restart

## FreeNAS tweak of FreeBSD setup
- Go to [192.168.1.2](http://192.168.1.2) FreeNAS
- System -> Tunables -> Add -> Variable: gateway_enable | Value: YES | Type: rc.conf
- Reboot

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

## Install proxmox

- USB key boot
- Install options
  - root-Color#What!
  - FQDN: pm1.2cld.net
  - IP: 192.168.1.221 NM: 24 GW: 192.168.1.1
 
## Monitoring
- [Monitoring, the Prometheus Way](https://www.youtube.com/watch?v=PDxcEzu62jk)
- [Best Practices - Metric and label naming](https://prometheus.io/docs/practices/naming/)
- [5 Best Practices for Using AI to Automatically Monitor Your Kubernetes Environment](https://www.anodot.com/blog/kubernetes-monitoring-best-practices/)
- [Anomaly Detection](https://www.anodot.com/blog/what-is-anomaly-detection/)
- [Prometheus - Exporters](https://github.com/prometheus/docs/blob/master/content/docs/instrumenting/exporters.md)
- [tbd]()
- [tbd]()

## Reference docs

- [ProxMox - Web_Interface_Via_Nginx_Proxy](https://pve.proxmox.com/wiki/Web_Interface_Via_Nginx_Proxy)
- [nginx ssl reverse proxy for jenkins](https://www.digitalocean.com/community/tutorials/how-to-configure-nginx-with-ssl-as-a-reverse-proxy-for-jenkins)
- [nginx freebsd install](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-freebsd-11-2)
- [2cld-NetworkLayout](https://docs.google.com/spreadsheets/d/1fIs0hXZehy1KZmvjHQ6srktOA0otWPfx2Bo0VUg2oa4/edit?ts=5cd30e41#gid=0) via christrees@gmail.com
- [2cld-DataCenterLayout](https://docs.google.com/spreadsheets/d/1QBA9OzsOhxs5W3kwlhxLZCmulFgd5uHMqu2qgrbMdxE/edit#gid=0) via admin@2cld.net (me)
