[edit]()

| External Service             | type | description | location    |
|------------------------------|------|-------------|-------------|
|      24.216.208.251 : 32400  | plex | gusHPlex    | sl |
| test.christrees.com :  2020  | ssh  | remote xfer | cf |
|      24.149.22.11   : 32400  | plex | cfPlex      | cf |

| Service admin Link  | type    | description | location    | mac |
|---------------------|---------|-------------|-------------|-----|
| [http://192.168.6.1/](http://192.168.6.1/) | ng | 854G-1 ng on subnet | cf:ng | 48-77-46-F6-BD-93 |
| [http://192.168.6.2/](http://192.168.6.2/) | sg | truenas sg on subnet | cf:sg vm on cg | 00-15-5D-00-C9-00 |
| [https://192.168.6.2:443/](https://192.168.6.2:443/) | sg | cf:sg truenas (https) sg on subnet | vm on cg | na |
| [https://192.168.6.3/](https://192.168.6.3/) | cg | cf:cg Hyper-V cg subnet | cg hardware | 10-C3-7B-46-0C-ED |
| ns2 | - | - | backup | na |
| ~~[http://192.168.6.6:81/](http://192.168.6.6:81/)~~ | ~~sg2~~ | sg2 on subnet | vm on cg2 | na |
| ~~[https://192.168.6.6:444/](https://192.168.6.6:444/)~~ | ~~sg2~~ | (https) sg2 on subnet | vm on cg2 | na |
| ~~[https://192.168.6.7:8006/](https://192.168.6.7:8006/)~~ | ~~cg2~~ | cg2 subnet | vm on cg2 | na |
| Plex | - | - | - | na |
| [https://192.168.6.3:32400/](https://192.168.6.3:32400/) | plex | cfPlex | app on cfPlex | 10-C3-7B-46-0C-ED |
|---------------------|---------|-------------|-------------|-----|
| catTemp | - | - | - | na |
| [https://192.168.0.201:32400/](https://192.168.0.201:32400/) | plex | cfPlex | app on sg2 proxmox | 10-C3-7B-46-0C-ED |
| [http://192.168.0.202:80/](http://192.168.0.202:80/) | sg2 | cf-sg2 on sl subnet | vm on cf-cg2 | 00-15-5D-02-71-03 |

---

| Service admin link | description |
|---|---|
| [status_devicetable](http://192.168.6.1/#/html/status/status_devicetable.html) | MAC Devices |
| [dhcp reservation](http://192.168.6.1/#/html/advanced/ip/advanced_ip_dhcpreservation.html) | DHCP Reservations |
| [port forwarding](http://192.168.6.1/#/html/advanced/security/advanced_security_advancedportforwarding.html) | Port Forwarding |
| [dmz hosting](http://192.168.6.1/#/html/advanced/security/advanced_security_dmzhosting.html) | DMZ |
| tbd | tbd |

## Media Ethernet Devices

| Network Name     | MAC Address       | IP         | port  | description     | rm | link |
|------------------|-------------------|------------|-------|-----------------|----|------|
|	na	                 | na                | na           | sw1p0 | Spectrum Modem  | sr | |
|	Archer_C7	           | 18-A6-F7-31-9C-07 | 192.168.0.1  |sw1int | TP-LINK AC1720  | sr | [admin](http://192.168.0.1/) |
|------------------|-------------------|--------------|-------|-----------------|----|------|
|	~~KathysRokuUltra~~	 | 84-EA-ED-A8-64-9x | na           | wifi  | KathysRokuUltra | lr | |
|	KathysRokuUltra	     | 84-EA-ED-A8-64-91 | 192.168.0.21 | sw2p1 | KathysRokuUltra | lr | |
|	TIVO-74600019083B6E2 | 00-11-D9-38-0B-FC | 192.168.0.22 | sw2p2 | Kathys160       | lr | |
| gusHPLaptop          | 00-23-8B-86-38-61 | 192.168.0.23 | sw2p3 | gusHPLaptop win10| lr | rmdesk [plex](http://192.168.0.23:32400) |
| gusGram              | AC-74-B1-02-FB-CF | 192.168.0.28 | wifi  | gusGram win11 i7| lr | rmdesk |
|	Portal-8B57B421F784  | A4-0E-2B-4C-EF-C7 | 192.168.0.29 | wifi  | portaltv        | lr | |
| pictureframe         | na                | na           | wifi  | picture frame   | lr | |
|------------------|-------------------|------------|-------|-----------------|----|------|
|	~~StevesRokuUltra~~	| 8C-49-62-0B-69-8C | 192.168.0.24 | ~~sw2p4~~ | StevesRokuUltra | sr | |
|	StevesRokuUltra	     | 8C-49-62-0B-69-8D | 192.168.0.14 | wifi  | StevesRokuUltra | sr | |
|	TIVO-8480001902B1749 | 00-11-D9-5F-47-83 | 192.168.0.15 | wifi  | Steves640       | sr | |
|	TIVO-8480001902B1749 | 00-11-D9-5F-47-82 | 192.168.0.11 | sw1p1 | Steves640       | sr | |
| TIVO-748000190569948 | 00-11-D9-35-02-A8 | 192.168.0.12 | sw1p2 | Steves320       | sr | |
|	HDHR-10802956	       | 00-18-DD-08-02-95 | 192.168.0.13 | sw2p4 | plexTuner       | sr | [admin](http://192.168.0.13/) |
| switch 1 to 2        | na                | na      |sw1p4-sw2p0 | sw1-sw2        |sr-lr| |
| switch 1 to 3        | basement run      | na      |sw1p3-sw2p0 | sw1-sw3        |sr-bm| |
|------------------|-------------------|------------|-------|-----------------|----|------|
|	cfPlex               | 10-C3-7B-46-0C-ED | 192.168.0.201 | sw1p1 | cfPlex chris's  | bm | rmdesk [plex](http://192.168.0.201:32400) |
|	cfsg2   	           | 00-15-5D-02-71-03 | 192.168.0.202 | vmbrg | trueNAS_vm-cfPlex | bm | [admin](http://192.168.0.202:8006/) |
|------------------|-------------------|------------|-------|-----------------|----|------|
|	cats-Mac-mini        | 7C-C3-A1-73-CC-A3 | 192.168.0.211 | wifi  | macmini  chris  | bm | |
|	catSurface   	       | 28-18-78-C7-FC-23 | 192.168.0.212 | wifi  | suface   chris  | bm | |
|	Pixel-6a    	       | 86-50-46-38-28-96 | 192.168.0.213 | wifi  | Pixel-6a chris  | bm | |
| FireTV cube          | A4-08-01-60-57-35 | 192.168.0.214 | wifi  | FireTV   chris  | bm | |

## Coax

| Coax name  | source   | destination | locations |
| ---------- |----------|-------------|-----------|
| ant feed   | main ant | coax amp    | attic to basement |
| spl01 feed | coax amp | spl01       | basement |
| sr feed    | spl01    | spl02       | basement to sr |
| Steves320 feed | spl02p1 | Steves320 Tivo ant | sr |
| plexTuner feed | spl02p2 | plexTuner ant | sr |
| Kathys160 feed | spl02p3 | Kathys160 ant | lr |

| Coax name  | source   | destination | locations |
| ---------- |----------|-------------|-----------|
| cable feed   | main cable | spl03 input | sr |
| spl03 feed | spl03p1 | spectrum modem       | sr |
| spl04 feed | spl03p2   | spl04 input       | sr |
| Steves640 feed | spl04p1 | Steves320 Tivo cable | sr |
| Kathys160 feed | spl04p2 | Kathys160 cable | sr |
| ?? feed | spl04p3 | ?? cable | sr |
| ?? feed | spl04p4 | ?? cable  | sr |
| Kathys160 feed | spl04p5 | ?? cable  | sr |

# Reference Docs
- sl network based on [https://netstack.org/](https://netstack.org/) sl.lan model [https://netstack.org/docs/lan/](https://netstack.org/docs/lan/)
  - ng.sl.lan network gateway [https://netstack.org/docs/lan/network/tp-link/](https://netstack.org/docs/lan/network/tp-link/)
  - sg.sl.lan storage gateway [https://netstack.org/docs/lan/storage/freenas/](https://netstack.org/docs/lan/storage/freenas/)
  - cg.sl.lan compute gateway [https://netstack.org/docs/lan/compute/proxmox/nswin11vm](https://netstack.org/docs/lan/compute/proxmox/nswin11vm)
 
---

- DHCP 192.168.0.100-199
- DNS 8.8.8.8
- GW 192.168.0.1 255.255.255.0
- SSID: TP-LINK_24 (18-A6-F7-31-9C-06)
- SSID: TP-LINK_9C05_5G (18-A6-F7-31-9C-05)

- WAN
```
18-A6-F7-31-9C-07
IP Address:	24.216.208.251	Dynamic IP
Subnet Mask:	255.255.248.0	 
Default Gateway:	24.216.208.1	  
DNS Server:	71.10.216.1 , 71.10.216.2
```

## port forward

| External | Internal | IP | detail |
|-------|-------|---------------|---|
| 32400	| 32400	| 192.168.0.23  | gusHPlex on gusHPLaptop | 
| 32800	| 32400	| 192.168.0.201 | cfPlex on win11 | 
|  2020 |    22 | 192.168.0.202 | cf-sg2 cattemp truenas | 


# OLD Crap REMOVE SOON
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
