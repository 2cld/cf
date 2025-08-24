# wf

[edit](https://github.com/2cld/cf/edit/master/docs/wf.md)
# Network Map

| External Service             | type | description | location    |
|------------------------------|------|-------------|-------------|
|      69.40.112.118   : 51821  | wg | [tbd]() | wf |
| wf.christrees.com :  2020  | 0.3 ssh  | cg | wf |
| [https://logger.trink.com/](https://logger.trink.com/) | cli logs | dg | hb |


## port forward

| External | Internal | IP | detail |
|-------|-------|---------------|---|
| 51821	| 51821	| 192.168.0.3 | wg tbd | 
|  2020 |    22 | 192.168.0.2 | ~~wf-sg truenas~~ disabled | 

## Internal Service 
- see https://one.dash.cloudflare.com/ network -> tunnels -> public hosts

| ns service admin    | type    | description | location    | mac |
|---------------------|---------|-------------|-------------|-----|
| [http://192.168.9.1/](http://192.168.9.1/) | ng | mikrotik [network gateway netstack](https://netstack.org/docs/lan/network/) on subnet | wf:ng | xx |
| ~~[http://192.168.9.2/](http://192.168.9.2/)~~ | sg | truenas  [storage gateway netstack](https://netstack.org/docs/lan/storage/) on na | wf:sg  | na |
| ~~[http://192.168.9.2:81/](http://192.168.9.2:81/)~~ | sg | truenas admin [storage admin netstack](http://192.168.6.2:81) on macci i3 | wf:sg  | na |
| [https://192.168.9.3:8006/](https://192.168.9.3:8006/) | cg | proxmox admin [cg - proxmox ui](https://192.168.9.3:8006/) on macci i3 | wf:cg  | na |
|---------------------|---------|-------------|-------------|-----|
| [https://192.168.9.11:9443/](https://192.168.9.11:9443/) | portainer | 100-docker | wf:ns | na |
|---------------------|---------|-------------|-------------|-----|
| [http://192.168.9.195/](http://192.168.9.195/) | ws | devwin10 | wf:ws  | na |
| [https://192.168.9.102:9090/](https://192.168.9.102:9090/) | ws | llscat | wf:ws | na |
| [http://192.168.0.30/](http://192.168.0.30/) | ws | casaos proxmox-lvm on macci i3 | wf:ws  | na |
| [http://192.168.0.30:xxx/](http://192.168.0.30:xxx/) | ws | portainser on casaos on macci i3 | wf:ws  | na |


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

