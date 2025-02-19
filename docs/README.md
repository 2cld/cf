[edit](https://github.com/2cld/cf/edit/master/docs/README.md)

- [ng2 - network map](./ng2/)
- [tbd]()
  
# Network Map

| External Service             | type | description | location    |
|------------------------------|------|-------------|-------------|
|      24.149.22.11   : 32400  | 6.3 plex | [cfPlex](https://24.149.22.11:32400) on CFPlex win11 i7 | cf ip changed 2024/12/?? |
|      24.149.22.11   : 32500  | 6.6 plex | [cfDVR](https://24.149.22.11:32500) on sg2 synology | cf |
|      24.149.22.11   : 32600  | 6.30 plex | [cfTV](https://24.149.22.11:32600) on CyberTruck win10 i7 | cf |
| test.christrees.com :  2020  | 6.2 ssh  | sg | cf |
| test.christrees.com :  2021  | 6.6 ssh  | sg2 | cf |
|      24.216.208.251 : 32400  | 0.6 plex | [slPlex](https://24.216.208.251:32400) on slwin11 win11 zeon | sl |
|      24.216.208.251 : 32500  | 0.9 plex | [slDVR](https://24.216.208.251:32500) on sg2 QNAP | sl |


## port forward

| External | Internal | IP | detail |
|-------|-------|---------------|---|
| 32400	| 32400	| 192.168.6.3 | ~~[cfPlex](https://24.149.22.11:32400)~~ on ~~[cfPlex local](https://192.168.6.3:32400)~~ win11 | 
| 32500	| 32400	| 192.168.6.6 | [cfDVR](https://24.149.22.11:32500) on [cfDVR local](https://192.168.6.6:32400) ds-411 | 
| 32600	| 32400	| 192.168.6.30 | [cfTV](https://24.149.22.11:32500) on [cfTV local](https://192.168.6.30:32400) Cybertruck | 
|  2020 |    22 | 192.168.6.2 | ~~cf-sg2 truenas~~ disabled | 
|  2021 |  2020 | 192.168.6.6 | cfDVR  | 

## Internal Service 
- see https://one.dash.cloudflare.com/ network -> tunnels -> public hosts
- see https://www.zerotier.com/ 

| ns service admin    | type    | description | location    | mac |
|---------------------|---------|-------------|-------------|-----|
| [http://192.168.6.1/](http://192.168.6.1/) | ng | 854G-1 [network gateway netstack](https://netstack.org/docs/lan/network/) on subnet | cf:ng | 48:77:46:F6:BD:93 |
| ~~[http://192.168.6.2/](http://192.168.6.2/)~~ | sg | truenas  [storage gateway netstack](https://netstack.org/docs/lan/storage/) on i3 | cf:sg  | b0:83:fe:65:80:80 |
| ~~[http://192.168.6.2:81/](http://192.168.6.2:81/)~~ | sg | truenas admin  [storage admin netstack](http://192.168.6.2:81) on i3 | cf:sg  | b0:83:fe:65:80:80 |
| ~~[http://192.168.6.2:30092/](http://192.168.6.2:30092/)~~ | sg | homer truenas app on i3 | cf:sg  | b0:83:fe:65:80:80 |
| ~~[http://192.168.6.2:30008/](http://192.168.6.2:30008/)~~ | sg | gitea truenas app on i3 | cf:sg  | b0:83:fe:65:80:80 |
| ~~[http://192.168.6.2:30013/](http://192.168.6.2:30013/)~~ | sg | jellyfin truenas app on i3 | cf:sg  | b0:83:fe:65:80:80 |
| ~~[http://192.168.6.3/](http://192.168.6.3/)~~ | cg | win11  [compute gateway netstack](https://netstack.org/docs/lan/compute/) cfPlex (win11) subnet | cg hardware (Hyper-V) | 10:C3:7B:46:0C:ED |
| res | - | - | - | na |
| ~~[http://192.168.6.4/](http://192.168.6.4/)~~ | - | - | - | 00:00:00:00:00:04 |
| ~~[http://192.168.6.5/](http://192.168.6.5/)~~ | - | - | - | 00:00:00:00:00:05 |
| ns2 | - | - | backup | na |
| [http://192.168.6.6:5000/ buadmin](http://192.168.6.6:5000/) | cfDVR-admin | cf:sg2 on ds411 synology | cf:sg2 | 00:11:32:08:c4:24 |
| [http://192.168.6.6:3000/ nsadmin](http://192.168.6.6:3000/) | cfDVR-gitea | cf:sg2 on ds411 synology | cf:sg2 | 00:11:32:08:c4:24 |
| [http://192.168.6.6:8081/](http://192.168.6.6:8081/) | cfDVR-metube | cf:sg2 on ds411 synology | cf:sg2 | 00:11:32:08:c4:24 |
| ~~[http://192.168.6.7:8006/](http://192.168.6.7:8006/)~~ local only inactive| sg2.cf.2cld.net | proxmox 8.1.4 | - | 00:00:00:00:00:xx |
| ~~[https://192.168.6.8/](https://192.168.6.8/)~~ local only inactive | bg | truenas old gh-garage | backup not running | 00:30:48:c7:82:b2 |
| ~~[https://192.168.6.9/](https://192.168.6.9/)~~ local only inactive | dg | git | vm on cg2 not running | 02:30:48:35:ea:a0 |
| [http://192.168.6.10:5000/ nsadmin](http://192.168.6.10:5000/) local only | nas | cfbu | cf | 00:11:32:12:b4:ed|
| Plex | - | - | - | na |
| ~~[https://192.168.6.3:32400/](https://192.168.6.3:32400/)~~ | plex | [cfPlex remote](https://24.149.22.11:32400) | cf:cg on cfPlex i7 win11 | 10:C3:7B:46:0C:ED |
| [https://192.168.6.6:32400/](https://192.168.6.6:32400/) | plex | [cfDVR remote](https://24.149.22.11:32500) | cf:cg on cfDVR synology ds411 | 00:11:32:08:c4:242 |
| [http://192.168.6.30:32400/](http://192.168.6.30:32400/) | cfTV | [Plex - cfTV](https://24.149.22.11:32600) | win10 i7 | 04:d9:f5:c8:c7:fc	|
| [http://192.168.6.11/](http://192.168.6.11/) | tuner | [HDHR-1080AD03](http://192.168.6.11/) | cf:tvswitch | 00:18:dd:08:0a:d0 |
| [http://192.168.6.12/](http://192.168.6.12/) | tv | FireTVMain | cf:wifi | 48:43:dd:74:f1:72	|
| [http://192.168.6.13/](http://192.168.6.13/) | tv | FireTVcat | cf:wifi | a4:08:01:60:57:35	|
|---------------------|---------|-------------|-------------|-----|
| CyberTruck win10 i7 | - | - | - | na |
| CyberTruck---w10os [http://192.168.6.30/](http://192.168.6.30/) | ws | cybertruck | win10 i7 | 04:d9:f5:c8:c7:fc	|
| plex-cfTV----w10os [http://192.168.6.30:32400/](http://192.168.6.30:32400/) | cfTV | [Plex - cfTV](https://24.149.22.11:32600) | win10 i7 | 04:d9:f5:c8:c7:fc	|
| ollama-------w10os [http://192.168.6.30:11434/](http://192.168.6.30:11434/) | cybertruck | cybertruck ollama | win10 i7 wsl | 04:d9:f5:c8:c7:fc	|
| portainer-wls-dker [http://192.168.6.30:9443/](http://192.168.6.30:9443/) | cybertruck | cybertruck portainer | win10 i7 wsl | 04:d9:f5:c8:c7:fc	|
| OI------wls-docker [http://192.168.6.30:8080/](http://192.168.6.30:8080/) | cybertruck | [https://chat.bradnordyke.com/](https://chat.bradnordyke.com/) | win10 i7 wsl | 04:d9:f5:c8:c7:fc	|
| HAOS----wls-docker [http://192.168.6.30:8123/](http://192.168.6.30:8123/) | cybertruck | Home Assistant | win10 i7 wsl | 04:d9:f5:c8:c7:fc	|
| CasaOS----old  ~~[http://192.168.6.30:20200/](http://192.168.6.30:20200/)~~ | cybertruck | cybertruck casaos | win10 i7 wsl | 04:d9:f5:c8:c7:fc	|
| Guacamole-old  ~~[http://192.168.6.30:8888/](http://192.168.6.30:8888/)~~ | cybertruck | [Fred -guacamole](https://fred.klopfenstein.org/) | win10 i7 wsl | 04:d9:f5:c8:c7:fc	|
| Workstations | - | - | - | na |
| [http://192.168.6.31/](http://192.168.6.31/) | ws | win11catvm | win11vm-cfPlex | 08:00:27:f1:c6:ee	|
| [http://192.168.6.32/](http://192.168.6.32/) | ws | catSurface | win10 i5 | 28:18:78:b7:be:b7	|
| [http://192.168.6.33/](http://192.168.6.33/) | ws | cats-Mac-mini | macOSX i7 | 3c:07:54:72:49:e2	|
| other | - | - | - | na |
| [http://192.168.6.40/](http://192.168.6.40/) | wifi | cellphone | pixel-6a | 88:54:1f:3a:77:03	|
| Security Cameras |---------|------|-------------|--|
| [http://192.168.6.161](http://192.168.6.161) | macDHCP | zmodo | camera web | - |
| [http://192.168.6.162](http://192.168.6.162) | macDHCP | zmodo | camera web | - |
| [http://192.168.6.163](http://192.168.6.163) | macDHCP | zmodo | camera web | - |
| [http://192.168.6.164](http://192.168.6.164) | macDHCP | zmodo | camera web | - |
| [http://192.168.6.165](http://192.168.6.165) | macDHCP | [zmodo remote](https://user.zmodo.com/#/home) | zmodo hub | - |

---

- [zmodo - web](https://user.zmodo.com/#/home) 
- [tbd laview - web]()
- [tbd blink - web]()
- [tbd energy - web]()
- [tbd vivitar - web]()
- tbd

| Service admin link | description |
|---|---|
| [ng.cfu.net - 854G-1 - http://192.168.6.1/](http://192.168.6.1/) | cfu pop router |
| [status_device table](http://192.168.6.1/#/html/status/status_devicetable.html) | MAC Devices |
| [dhcp reservation](http://192.168.6.1/#/html/advanced/ip/advanced_ip_dhcpreservation.html) | DHCP Reservations |
| [port forwarding](http://192.168.6.1/#/html/advanced/security/advanced_security_advancedportforwarding.html) | Port Forwarding |
| [dmz hosting](http://192.168.6.1/#/html/advanced/security/advanced_security_dmzhosting.html) | DMZ |
| [Firewall Rules](http://192.168.6.1/#/html/advanced/security/advanced_security_firewallsettings.html) | Firewall Rules |
| tbd | tbd |

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

## Coax

| Coax name  | source   | destination | locations |
| ---------- |----------|-------------|-----------|
| cable feed | fiber box | spl01    | box to spl01 |
| HDHR-1080AD03 feed | spl01p1 | tuner | bm |
| LivingRoom feed | spl01p2 | tv | lr |
| LivingRoom feed | spl01p3 | none | lr |
| Bedroom feed | spl01p4 | tv | br |
| basement feed | spl01p5 | tv | bm |

# Reference Docs
- sl network based on [https://netstack.org/](https://netstack.org/) sl.lan model [https://netstack.org/docs/lan/](https://netstack.org/docs/lan/)
  - ng.sl.lan network gateway [https://netstack.org/docs/lan/network/tp-link/](https://netstack.org/docs/lan/network/tp-link/)
  - sg.sl.lan storage gateway [https://netstack.org/docs/lan/storage/freenas/](https://netstack.org/docs/lan/storage/freenas/)
  - cg.sl.lan compute gateway [https://netstack.org/docs/lan/compute/proxmox/nswin11vm](https://netstack.org/docs/lan/compute/proxmox/nswin11vm)

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

## User Storage DVR

| External Service             | type | description | location    |
|------------------------------|------|-------------|-------------|
|      24.149.22.11   : 32400  | plex | [cfPlex](https://24.149.22.11:32400) | cf |
|      24.149.22.11   : 32500  | plex | [cfDVR](https://24.149.22.11:32500)  | cf |
| test.christrees.com :  2020  | ssh  | cf-sg2 | cf |
| test.christrees.com :  2021  | ssh  | cfDVR | cf |

## cfPlex Storage Mapping (10.147.17.228 - 192.168.6.2)

| cfPlex 10.147.17.228 /192.168.6.2 | Plex | Plex Libraries | location |
|-----------------------------------|------|-------------|-------------|
| G: \\10.147.17.66\gusHPlexSFEPart | gusHPlex | [gusHPlexG.md](./gusHPlexG) remoted storage | sl |
| H: \\192.168.6.2\ghpool           | cfPlex  | TrueNAS ghpool storage | cf |
| M: \\192.168.6.2\MediaShare       | cfPlex  | TrueNAS MediaShare storage | cf |
| N: \\192.168.6.2\catbox           | cfPlex  | TrueNAS catbox in catpool storage | cf |
| O: \\192.168.6.10\plexnsds        | cfPlex  | [cfPlex0.md](./cfPlex0) StarTrek storage | cf |
| P: \\192.168.6.6\pshare           | cfDVR | Synology NAS storage | cf |

- [Plex Naming Conventions and Library guide](https://www.oliviertravers.com/plex-complex-libraries-ultimate-media-server/)
  
### cf-s2 trueNAS vm on win11 cfPlex
```
% ssh -p 2020 trink@test.christrees.com
trink@cf-sg2:~$ pwd
/mnt/catpool/users/trink
trink@cf-sg2:~$ ls /mnt/catpool/trink/trinkDVR/
'NBC Nightly News With Lester Holt (2015)'
trink@cf-sg2:~$ 
```

### cfDVR Synology 411 running plex in jail
```
 % ssh -p 2021 trink@test.christrees.com
trink@cfDVR:~$ ls /volume1/pshare/trinkDVR/
NBC Nightly News With Lester Holt (2015)
trink@cfDVR:~$ 
```

# Grid Network - [cat-ghadmin-grid](https://my.zerotier.com/network/d5e5fb65371eb4a4)

| ns service admin    | type    | description | location    | mac |
|---------------------|---------|-------------|-------------|-----|
| [http://10.147.17.1/](http://10.147.17.1/) | ws | cattvwin10 | cf:ws |tb |
| [http://10.147.17.127/](http://10.147.17.127/) | ws | catghwin10 | cf:ws |tb |
| [http://10.147.17.228/](http://10.147.17.228/) | ws | cfplex | cf:ws |tb |
| [http://10.147.17.59/](http://10.147.17.59/) | ws | catmini | cf:ws |tb |
| [http://10.147.17.219/](http://10.147.17.219/) | ws | CyberTruck | cf:ws | tb |
| [http://10.147.17.223/](http://10.147.17.223/) | ws | catsurface | cf:ws | tb |

# Storage Network - [cattv](https://my.zerotier.com/network/52b337794f721ef7)

| ns service admin    | type    | description | location    | mac |
|---------------------|---------|-------------|-------------|-----|
| [http://10.147.19.1/](http://10.147.19.1/) | ws | cattvwin10 | cf:ws |tb |
| [http://10.147.19.127/](http://10.147.19.127/) | ws | catghwin10 | cf:ws |tb |
| [http://10.147.19.228/](http://10.147.19.228/) | ws | cfplex | cf:ws |tb |
| [http://10.147.19.59/](http://10.147.19.59/) | ws | catmini | cf:ws |tb |
| [http://10.147.19.25/](http://10.147.19.25/) | sg | sg2 | cf:ws | [qnap](https://netstack.org/docs/lan/storage/qnap/) TS-431 driver issue |
| [http://10.147.19.62/](http://10.147.19.62/) | ws | catqnapsg2 | cf:ws | old [qnap](https://netstack.org/docs/lan/storage/qnap/) TS-431 |
| [http://10.147.19.62:8080/](http://10.147.19.62:8080/) | ws | catqnapsg2 | cf:ws | [qnap](https://netstack.org/docs/lan/storage/qnap/) portal |

### Reference
- Domain [https://domains.google.com/registrar/](https://domains.google.com/registrar/)
  - DNS [https://domains.google.com/registrar/christrees.com/dns](https://domains.google.com/registrar/christrees.com/dns)
- [https://hsve.org/proxmox-gpu-passthrough-to-windows-10-11/](https://hsve.org/proxmox-gpu-passthrough-to-windows-10-11/)
- tbd
- [Plex downloads](https://www.plex.tv/media-server-downloads/)
  - Plex 1.28.2 for OSX 10.9
  - [Plex remote client network issue](https://www.devwithimagination.com/2019/08/21/plex-docker-and-the-problem-of-always-appearing-as-remote/)
  - [Plex remote access pfsense configs](https://www.thesmarthomebook.com/2020/04/16/fixing-remote-access-for-plex-in-pfsense/)
  - [Plex-Reverse-Proxy-for-Docker](https://github.com/fmillion/docs/blob/master/Plex-Reverse-Proxy-for-Docker.md)
- [ZeroTier downloads](https://www.zerotier.com/download/)
  - [cattv - network - 52b337794f721ef7](https://my.zerotier.com/network/52b337794f721ef7) ghadmin
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
