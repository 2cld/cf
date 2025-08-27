# wf

[edit](https://github.com/2cld/cf/edit/master/docs/wf.md)
# Network Map

| External Service             | type | description | location    |
|------------------------------|------|-------------|-------------|
|   69.40.112.118   : 51821  | wg | [tbd]() | wf |
| wf.christrees.com :  2020  | 0.3 ssh  | cg | wf |
| [https://logger.trink.com/](https://logger.trink.com/) | cli logs | dg | hb |


## local connect

| External | Internal | IP | detail |
|-------|-------|---------------|---|
| xx | xx | 98.97.4.249 | Public |
| xx | xx | ~~100.113.125.255/10~~ | ~~Public~~ old windstream |
| xx | xx | [192.168.4.1/24](http://192.168.4.1/) | TreesAES [starlink](https://www.starlink.com/) |
| xx | xx | TreesAES | TreesAES 5G wifi |
| xx | xx | IoTrees | IoTrees 2.5G wifi |
| xx | xx | mt-wifi | mt-wifi mikrotik 5G wifi |
| xx | xx | 192.168.4.165 | iPhone - TreesAES 5G wifi phone app required to access router |
| xx | xx | 192.168.4.145 -> 192.168.9.1 | [mikrotik](https://netstack.org/docs/lan/network/mikrotik/) - wired |


## Internal Service 
- see https://one.dash.cloudflare.com/ network -> tunnels -> public hosts

| ns service admin    | ns | [cf](https://one.dash.cloudflare.com/) | description | location | [zt](https://my.zerotier.com/) |
|---------------------|--|------|-------------|----|-----|
| [http://192.168.9.1/](http://192.168.9.1/) ng-ip  | [ng](https://netstack.org/docs/lan/network/) | xx | [ns mikrotik](https://netstack.org/docs/lan/network/mikrotik/) on [network gateway netstack](https://netstack.org/docs/lan/network/) on subnet | wf:ng | xx |
| ng [DHCP Leases](http://192.168.9.1/webfig/#IP:DHCP_Server.Leases) | [ng](https://netstack.org/docs/lan/network/) | xx | [mikrotik](https://netstack.org/docs/lan/network/mikrotik/) DHCP Leases | wf:ng | xx |
| ng [DHCP Used](http://192.168.9.1/webfig/#IP:Pool.Used_Addresses) | [ng](https://netstack.org/docs/lan/network/) | xx | [mikrotik](https://netstack.org/docs/lan/network/mikrotik/) DHCP used | wf:ng | xx |
| ng [WiFi mt-wifi](http://192.168.9.1/webfig/#Wireless.Security_Profiles) | [ng](https://netstack.org/docs/lan/network/) | xx | [mikrotik](https://netstack.org/docs/lan/network/mikrotik/) mt-wifi | wf:ng | xx |
|---------------------|--|------|-------------|----|-----|
| [http://192.168.9.2/](http://192.168.9.2/) sg-ip | [sg](https://netstack.org/docs/lan/storage/) | xx | sg  [storage gateway netstack](https://netstack.org/docs/lan/storage/) on synology | wf:sg  | 10.147.17.209 |
| sg [synology AdminPortal:5000/](http://192.168.9.2:5000/) | [sg](https://netstack.org/docs/lan/storage/) | [sg.klopfenstein.org](https://sg.klopfenstein.org/) | sg buadmin portal | wf:sg  | [10.147.17.209:5000/](http://10.147.17.209:5000/) |
| sg PkgInstDocker [gitea:3000/](http://192.168.9.2:3000/) | [sg](https://netstack.org/docs/lan/storage/) | [gitea.klopfenstein.org](https://gitea.klopfenstein.org/) | sg gitea portal | wf:sg  | [10.147.17.209:3000/](http://10.147.17.209:3000/) |
| sg PkgInstDocker [cf-metube:8081/](http://192.168.9.2:8081/) | [sg](https://netstack.org/docs/lan/storage/) | [metube.klopfenstein.org](https://metube.klopfenstein.org/) | sg cf-metube portal | wf:sg  | [10.147.17.209:8081/](http://10.147.17.209:8081/) |
| sg PkgInstDocker [plextube:32400/](http://192.168.9.2:32400/) | [sg](https://netstack.org/docs/lan/storage/) | xx | sg plextube portal on synology | wf:sg  | [10.147.17.209:32400/](http://10.147.17.209:32400/) |
|---------------------|--|------|-------------|----|-----|
| [https://192.168.9.3/](https://192.168.9.3/) cg-ip  | cg | xx | proxmox admin [cg - proxmox ui](https://192.168.9.3:8006/) on ASUS i5 | wf:cg  | na |
| cg [proxmox AdminPortal:8006/](https://192.168.9.3:8006/) | cg | xx | proxmox admin [cg - proxmox ui](https://192.168.9.3:8006/) on ASUS i5 | wf:cg  | na |
| cg-vm [https://192.168.9.11:3000/](https://192.168.9.11:3000/) | cg  | xx | gitea 100-docker-vm proxmox | wf:ns | na |
| cg-vm [https://192.168.9.11:9443/](https://192.168.9.11:9443/) | cg  | xx | portainer 100-docker-vm proxmox | wf:ns | na |
| cg-vm [https://192.168.9.11:9090/](https://192.168.9.11:9090/) | cg  | xx | cockpit 100-docker-vm proxmox | wf:ns | na |
| cg-vm [https://192.168.9.102:9090/](https://192.168.9.102:9090/) | cg  | xx | ws llscat cockpit portal | wf:ws | na |
|---------------------|--|------|-------------|----|-----|
| [http://192.168.9.195/](http://192.168.9.195/) ws-ip | ws | xx | devwin10 | wf:ws  | 10.147.17.165 |


---
---

## old windstream
| Service admin link | description |
|---|---|
| [Windstream - T3200 - http://192.168.0.1/](http://192.168.0.1/) | wf pop router |
| [status_device table](http://192.168.0.1/modemstatus_lanstatus.html) | MAC Devices |
| [dhcp reservation](http://192.168.0.1/advancedsetup_dhcpreservation.html) | DHCP Reservations |
| [port forwarding](http://192.168.0.1/advancedsetup_advancedportforwarding.html) | Port Forwarding |
| [dmz hosting](http://192.168.0.1/advancedsetup_dmzhosting.html) | DMZ |
| [Firewall Rules](http://192.168.0.1/advancedsetup_firewallsettings.html) | Firewall Rules |
| tbd | tbd |

- DHCP 192.168.0.200-254
- DNS 8.8.8.8
- GW 192.168.0.1 255.255.255.0

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

