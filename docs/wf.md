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
| xx | xx | 100.113.125.255/10 | Public |
| xx | xx | [192.168.4.1/24](http://192.168.4.1/) | TreesAES starlink |
| xx | xx | TreesAES | TreesAES 5G wifi |
| xx | xx | IoTrees | IoTrees 5G wifi |
| xx | xx | mt-wifi | mt-wifi mikrotik 5G wifi |
| xx | xx | [192.168.4.165/24](http://192.168.4.165/) | iPhone - TreesAES 5G wifi phone app required to access router |


## Internal Service 
- see https://one.dash.cloudflare.com/ network -> tunnels -> public hosts

| ns service admin    | type    | description | location    | mac |
|---------------------|---------|-------------|-------------|-----|
| [http://192.168.9.1/](http://192.168.9.1/) ng-ip  | ng | mikrotik [network gateway netstack](https://netstack.org/docs/lan/network/) on subnet | wf:ng | xx |
| ng [DHCP Leases](http://192.168.9.1/webfig/#IP:DHCP_Server.Leases) | ng | mikrotik DHCP Leases | wf:ng | xx |
| ng [DHCP Used](http://192.168.9.1/webfig/#IP:Pool.Used_Addresses) | ng | mikrotik DHCP used | wf:ng | xx |
| ng [WiFi mt-wifi](http://192.168.9.1/webfig/#Wireless.Security_Profiles) | ng | mikrotik mt-wifi | wf:ng | xx |
|---------------------|---------|-------------|-------------|-----|
| [http://192.168.9.2/](http://192.168.9.2/) sg-ip | sg | sg  [storage gateway netstack](https://netstack.org/docs/lan/storage/) on synology | wf:sg  | na |
| sg [synology AdminPortal:5000/](http://192.168.9.2:5000/) | sg | sg buadmin portal [sg.klopfenstein.org](https://sg.klopfenstein.org/) | wf:sg  | na |
| sg PkgInstDocker [gitea:3000/](http://192.168.9.2:3000/) | sg | sg gitea portal on [gitea.klopfenstein.org](https://gitea.klopfenstein.org/) | wf:sg  | na |
| sg PkgInstDocker [cf-metube:8081/](http://192.168.9.2:8081/) | sg | sg cf-metube portal on [metube.klopfenstein.org](https://metube.klopfenstein.org/) | wf:sg  | na |
| sg PkgInstDocker [plextube:34200/](http://192.168.9.2:34200/) | sg | sg plextube portal on synology | wf:sg  | na |
|---------------------|---------|-------------|-------------|-----|
| [https://192.168.9.3/](https://192.168.9.3/) cg-ip  | cg | proxmox admin [cg - proxmox ui](https://192.168.9.3:8006/) on ASUS i5 | wf:cg  | na |
| cg [proxmox AdminPortal:8006/](https://192.168.9.3:8006/) | cg | proxmox admin [cg - proxmox ui](https://192.168.9.3:8006/) on ASUS i5 | wf:cg  | na |
| cg-vm [https://192.168.9.11:3000/](https://192.168.9.11:3000/) | gitea | 100-docker-vm proxmox | wf:ns | na |
| cg-vm [https://192.168.9.11:9443/](https://192.168.9.11:9443/) | portainer | 100-docker-vm proxmox | wf:ns | na |
| cg-vm [https://192.168.9.11:9090/](https://192.168.9.11:9090/) | cockpit | 100-docker-vm proxmox | wf:ns | na |
| cg-vm [https://192.168.9.102:9090/](https://192.168.9.102:9090/) | ws | llscat cockpit portal | wf:ws | na |
|---------------------|---------|-------------|-------------|-----|
| [http://192.168.9.195/](http://192.168.9.195/) ws-ip | ws | devwin10 | wf:ws  | na |


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

