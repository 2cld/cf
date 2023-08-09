[edit]()

[edit old source on cf.christrees.com](https://github.com/christrees/cf.christrees.com/edit/main/ns/README.md)

| Service admin Link  | type    | description | location    |
|---------------------|---------|-------------|-------------|
| [http://192.168.2.1/](http://192.168.2.1/) | ng | pfsense ng on subnet | vm on cg |
| [http://192.168.2.2/](http://192.168.2.2/) | sg | truenas sg on subnet | vm on cg |
| [https://192.168.2.2:443/](https://192.168.2.2:443/) | sg | truenas (https) sg on subnet | vm on cg |
| [https://192.168.2.3:8006/](https://192.168.2.3:8006/) | cg | proxmox cg subnet | cg hardware |
| - | - | - | - |
| [http://192.168.2.6:81/](http://192.168.2.6:81/) | sg2 | truenas2 sg2 on subnet | vm on cg2 |
| [https://192.168.2.6:444/](https://192.168.2.6:444/) | sg2 | truenas2 (https) sg2 on subnet | vm on cg2 |
| [https://192.168.2.7:8006/](https://192.168.2.7:8006/) | cg2 | proxmox cg2 subnet | vm on cg2 |
| - | - | - | - |
| [https://192.168.2.99:32400/](https://192.168.2.99:32400/) | plex | plex on ghwin11 | app on ghwin11 |
| [https://192.168.2.100:32400/](https://192.168.2.100:32400/) | plex| plex on cattvwin10 | app on cattvwin10 |
| [http://192.168.2.105:32400](http://192.168.2.105:32400) | plex | bs01ds411 plex web | 32400 on IP plex on bs01ds411 synology nas |
| - | - | - | - |
| [http://192.168.2.102](http://192.168.2.102) | tuner | HDHR-1080AD03 web | silicondust hw |
| - | - | - | - |
| [http://192.168.2.103/](http://192.168.2.103/) | app | nginx proxy default | vm on cg |
| [http://192.168.2.103:81](http://192.168.2.103:81) | app | nginx proxy admin | vm on cg |
| [http://192.168.2.103:9000](http://192.168.2.103:9000) | app | portainer admin | portainer admin on cg docker 103 |
| [http://192.168.2.103:32400](http://192.168.2.103:32400) | app | dockerplex web | 32400 on IP plex on portainer |
| [http://192.168.2.2:32500](http://192.168.2.2:32500) | app | tnasplex web | 32500 on IP plex on portainer |
| - | - | - | - |
| [http://192.168.2.105:5000](http://192.168.2.105:5000) | bs01 | bs01ds411 admin web | 5000 on admin web bs01ds411 synology nas |
| [http://192.168.6.159:5000/](http://192.168.6.159:5000/) | bs | nsDiskStation web | 5000 on DS212i Synology |

### Notes
- [framework laptop https://frame.work/](https://frame.work/)
- [google remote](https://remotedesktop.google.com/access)
- [render network diagram in github](https://github.com/christrees/cf.christrees.com/blob/main/ns/cfnetwork.md)

### quick
---
- [cattvwin10 http://test.christrees.com:32400/](http://test.christrees.com:32400/)
- [dockerplex http://test.christrees.com:32500/](http://test.christrees.com:32500/)
- [tnasplex   http://test.christrees.com:32600/](http://test.christrees.com:32600/)
- [bs01ds411  http://test.christrees.com:32700/](http://test.christrees.com:32700/)

---
- [zmodo - web](https://user.zmodo.com/#/home) 
- [tbd laview - web]()
- [tbd blink - web]()
- [tbd energy - web]()
- [tbd vivitar - web]()
- tbd

---

# WIP Portals
- [https://cf.christrees.com/](https://cf.christrees.com/)
- [http://blog.christrees.com/wip/trinkcolab](http://blog.christrees.com/wip/trinkcolab)
- [http://test.christrees.com/](http://test.christrees.com/) 
- [https://whatismyipaddress.com/ip/24.149.22.11](https://whatismyipaddress.com/ip/24.149.22.11) - 24.149.22.11
- [https://whatismyipaddress.com/](https://whatismyipaddress.com/)
- [https://www.plex.tv/](https://www.plex.tv/)
- [https://www.plex.tv/claim/](https://www.plex.tv/claim/)
- [https://www.cfu.net/tv-internet/tv-service-info/channel-guide](https://www.cfu.net/tv-internet/tv-service-info/channel-guide)
- [cattvwin10 channel map](https://docs.google.com/spreadsheets/d/1wjN1_N5Vjji6NQgE3DXi4D-S76sAHppQrdXsqh5qX2E/edit#gid=0) 
- [tbd]()

## 192.168.6.0/24 gw [http://192.168.6.1/](http://192.168.6.1/)

| web proxy    |   Link  | type | description |
|--------------|---------|------|-------------|
| cfu | [http://192.168.6.1/](http://192.168.6.1/) | static | cfu fw19 |
| pfsense | [http://192.168.6.103:91/](http://192.168.6.103:91/) | to 192.168.2.1:80 | gui fw for 192.168.2.0/24 |
| nginx default | [http://192.168.6.103/](http://192.168.6.103/) | static | default nginx proxy page running in portainer |
| nginx proxy admin | [http://192.168.6.103:81](http://192.168.6.103:81) | static | admin for nginx running in portainer |
| -- _Proxy ADMIN_ |---------|------|-------------|
| cg proxmox admin | [https://192.168.6.103:8006](https://192.168.6.103:8006) | to 192.168.2.3:8006 | cg proxmox |
| cg2 proxmox admin | [https://192.168.6.103:8007](https://192.168.6.103:8007) | to 192.168.2.7:8006 | cg2 proxmox |
| portainer admin | [http://192.168.6.103:9000](http://192.168.6.103:9000) | static | portainer admin on proxmox docker 103 |
| truenas-cg admin | [https://192.168.6.103:9090](https://192.168.6.103:9090) | to 192.168.2.2:443 | TrueNAS-cg on proxmox truenas 102 |
| truenas-cg ssh | ssh 192.168.6.103:2021 | to 192.168.2.2:22 | ssh to truenas-cg |
| truenas-cg2 admin | [https://192.168.6.103:9091](https://192.168.6.103:9091) | to 192.168.2.6:444 | TrueNAS-cg2 on proxmox truenas 103 |
| truenas-cg2 ssh | ssh 192.168.6.103:2022 | to 192.168.2.6:22 | ssh to truenas-cg2 |
| bs01ds411 web | [http://192.168.6.103:5000/](http://192.168.6.103:5000/) | to 192.168.2.105:5000 | DS411 Synology |
| nsDiskStation web | [http://192.168.6.159:5000/](http://192.168.6.159:5000/) | macDHCP | DS212i Synology |
| -- TV Admin |---------|------|-------------|
| dockerplex web | [http://192.168.6.103:32400](http://192.168.6.103:32400) | static | 32400 on IP plex on portainer |
| tnasplex web | [http://192.168.6.103:32500](http://192.168.6.103:32500) | static | 32500 on IP plex on portainer |
| bs01ds411 web | [http://192.168.6.103:32700](http://192.168.6.103:32700) | static | 32700 on IP plex on bs01ds411 synology nas |
| cattvwin10 web | [http://192.168.6.180:32400](http://192.168.6.180:32400) | macDHCP | 32600 on IP plex on cattvwin10 |
| nsDiskStation web | [http://192.168.6.159:5000/](http://192.168.6.159:5000/) | macDHCP | DS212i Synology |
| HDHR-10802956 web | [http://192.168.6.160](http://192.168.6.160) | macDHCP | silicondust tuner |
| Security Cameras |---------|------|-------------|
| zmodo camera web | [http://192.168.6.161](http://192.168.6.161) | macDHCP | zmodo |
| zmodo camera web | [http://192.168.6.162](http://192.168.6.162) | macDHCP | zmodo |
| zmodo camera web | [http://192.168.6.163](http://192.168.6.163) | macDHCP | zmodo |
| zmodo camera web | [http://192.168.6.164](http://192.168.6.164) | macDHCP | zmodo |
| zmodo hub web | [http://192.168.6.165](http://192.168.6.165) | macDHCP | zmodo |


## 192.168.2.0/24 gw [http://192.168.2.1/](http://192.168.2.1/)
  
| web proxy    |   Link  | type | description |
|--------------|---------|------|-------------|
| pfsense | [http://192.168.2.1/](http://192.168.2.1/) | static | pfsense ng on subnet |
| truenas | [http://192.168.2.2/](http://192.168.2.2/) | macDHCP | truenas sg on subnet |
| truenas | [http://192.168.2.2:443/](http://192.168.2.2:443/) | macDHCP | truenas sg on subnet |
| truenas2 | [http://192.168.2.6:81/](http://192.168.2.6:81/) | macDHCP | truenas sg on subnet |
| truenas2 | [https://192.168.2.6:444/](https://192.168.2.6:444/) | macDHCP | truenas sg on subnet |
| cg-proxmox | [https://192.168.2.3:8006/](https://192.168.2.3:8006/) | static macres | proxmox cg subnet |
| cg2-proxmox | [https://192.168.2.7:8006/](https://192.168.2.7:8006/) | static macres | proxmox cg subnet |
| ghwin11 plex | [https://192.168.2.99:32400/](https://192.168.2.99:32400/) | macDHCP | plex on ghwin11 |
| cattvwin10 plex | [https://192.168.2.100:32400/](https://192.168.2.100:32400/) | macDHCP | plex on cattvwin10 |
| HDHR-1080AD03 web | [http://192.168.2.102](http://192.168.2.102) | macDHCP | tuner |
| nginx default | [http://192.168.2.103/](http://192.168.2.103/) | macDHCP | default nginx proxy page running in portainer |
| nginx proxy admin | [http://192.168.2.103:81](http://192.168.2.103:81) | macDHCP | admin for nginx running in portainer |
| portainer admin | [http://192.168.2.103:9000](http://192.168.2.103:9000) | macDHCP | portainer admin on proxmox docker 103 |
| dockerplex web | [http://192.168.2.103:32400](http://192.168.2.103:32400) | macDHCP | 32400 on IP plex on portainer |
| tnasplex web | [http://192.168.2.2:32500](http://192.168.2.2:32500) | static | 32500 on IP plex on portainer |
| bs01ds411 plex web | [http://192.168.2.105:32400](http://192.168.2.105:32400) | macDHCP | 32400 on IP plex on bs01ds411 synology nas |
| bs01ds411 admin web | [http://192.168.2.105:5000](http://192.168.2.105:5000) | macDHCP | 5000 on admin web bs01ds411 synology nas |

---

| admin web    |   Link  | description |
|--------------|---------|-------------|
| pfsense | [http://192.168.2.1/](http://192.168.2.1/) | pfsense ng on subnet |
| -- DHCP-Lease | [http://192.168.2.1/status_dhcp_leases.php?all=1](http://192.168.2.1/status_dhcp_leases.php?all=1) | DHCP-Lease |
| truenas | [http://192.168.2.2/](http://192.168.2.2/) | truenas sg on subnet |
| -- pools | [http://192.168.2.2/](http://192.168.2.2/) | truenas sg on subnet |
| proxmox | [https://192.168.2.3:8006/](https://192.168.2.3:8006/) | proxmox cg subnet |
| -- storage | [https://192.168.2.3:8006/](https://192.168.2.3:8006/) | proxmox cg subnet |
| nginx proxy admin | [http://192.168.2.103:81](http://192.168.2.103:81) | admin for nginx running in portainer |
| -- sites | [http://192.168.2.103:81](http://192.168.2.103:81) | admin for nginx running in portainer |
| portainer admin | [http://192.168.2.103:9000](http://192.168.2.103:9000) | portainer admin on proxmox docker 103 |
| -- admin | [http://192.168.2.103:9000](http://192.168.2.103:9000) | portainer admin on proxmox docker 103 |
| dockerplex web | [http://192.168.2.103:32400](http://192.168.2.103:32400) | 32400 on IP plex on portainer |
| -- admin | [http://192.168.2.103:32400](http://192.168.2.103:32400) | 32400 on IP plex on portainer |
| tnasplex web | [http://192.168.2.2:32500](http://192.168.2.2:32500) | 32500 on IP plex on portainer |
| -- admin | [http://192.168.2.2:32500](http://192.168.2.2:32500) | 32500 on IP plex on portainer |
| HDHR-1080AD03 web | [http://192.168.2.102](http://192.168.2.102) | tuner |
| -- web | [http://192.168.2.102](http://192.168.2.102) | tuner |
| bs01ds411 plex web | [http://192.168.2.105:32400](http://192.168.2.105:32400) | 32400 on IP plex on bs01ds411 synology nas |
| -- admin web | [http://192.168.2.105:5000](http://192.168.2.105:5000) | 5000 on buadmin web bs01ds411 nas |

---
- Domain [https://domains.google.com/registrar/](https://domains.google.com/registrar/)
  - DNS [https://domains.google.com/registrar/christrees.com/dns](https://domains.google.com/registrar/christrees.com/dns)
- Public [http://24.149.22.11/](http://24.149.22.11/) - as of 20230117

---

## DMZ LAN local
- cfu pop router [ng.cfu.net - 854G-1 - http://192.168.6.1/](http://192.168.6.1/)
  - [current devices](http://192.168.6.1/#/html/status/status_devicetable.html)
  - [DHCP Reservations](http://192.168.6.1/#/html/advanced/ip/advanced_ip_dhcpreservation.html)
  - [Port Forwarding](http://192.168.6.1/#/html/advanced/security/advanced_security_advancedportforwarding.html)
    - 32400 to 32400	192.168.6.180 (cattvWin10 plex)	TCP	32600 to 32600	All IP Addresses	
    - 80    to 80	    192.168.6.103 (nginx proxy man) TCP	80    to 80   	All IP Addresses
    - 32400 to 32400	192.168.6.103 (dockerplex plex)	TCP	32400 to 32400	All IP Addresses	
  - [Firewall Rules](http://192.168.6.1/#/html/advanced/security/advanced_security_firewallsettings.html)


### Reference
- [https://hsve.org/proxmox-gpu-passthrough-to-windows-10-11/](https://hsve.org/proxmox-gpu-passthrough-to-windows-10-11/)
- tbd
- [Plex downloads](https://www.plex.tv/media-server-downloads/)
  - Plex 1.28.2 for OSX 10.9
  - [Plex remote client network issue](https://www.devwithimagination.com/2019/08/21/plex-docker-and-the-problem-of-always-appearing-as-remote/)
  - [Plex remote access pfsense configs](https://www.thesmarthomebook.com/2020/04/16/fixing-remote-access-for-plex-in-pfsense/)
  - [Plex-Reverse-Proxy-for-Docker](https://github.com/fmillion/docs/blob/master/Plex-Reverse-Proxy-for-Docker.md)
- [ZeroTier downloads](https://www.zerotier.com/download/)
  - [cattv - network - 52b337794f721ef7](https://my.zerotier.com/network/52b337794f721ef7) ghadmin
  - [tbd]()
- [pfsense monitor bandwidth useage](https://docs.netgate.com/pfsense/en/latest/monitoring/graphs/bandwidth-usage.html)
- [https://adamtheautomator.com/nginx-proxy-manager/](https://adamtheautomator.com/nginx-proxy-manager/)
- [portainer with nginx proxy manager - install](https://www.howtoforge.com/how-to-install-and-use-portainer-for-docker-management-with-nginx-proxy-manager/)
- [https://nginxproxymanager.com/guide/#quick-setup](https://nginxproxymanager.com/guide/#quick-setup)
- [https://nginxproxymanager.com/advanced-config/#best-practice-use-a-docker-network](https://nginxproxymanager.com/advanced-config/#best-practice-use-a-docker-network)
- [https://github.com/2cld/netstack/tree/master/docs/lan](https://github.com/2cld/netstack/tree/master/docs/lan)
- [https://app.diagrams.net/#Hpitimon%2FspComNet%2Fmain%2Fproxmox22](https://app.diagrams.net/#Hpitimon%2FspComNet%2Fmain%2Fproxmox22)
- [https://www.virtualizationhowto.com/2022/08/pfsense-proxmox-install-process-and-configuration/](https://www.virtualizationhowto.com/2022/08/pfsense-proxmox-install-process-and-configuration/)
- [https://tailscale.com/compare/zerotier/](https://tailscale.com/compare/zerotier/)
- [https://login.tailscale.com/admin/welcome](https://login.tailscale.com/admin/welcome) - ghadmin@horseoff.com login-with-google
- [tbd]()

---

---
