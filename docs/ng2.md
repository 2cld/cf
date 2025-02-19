[edit]()
# Network Map

| External Service             | type | description | location    |
|------------------------------|------|-------------|-------------|
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
| [http://192.168.9.1/](http://192.168.9.1/) | ng2 | 854G-1 [network gateway netstack](https://netstack.org/docs/lan/network/) on subnet | cf:ng | 48:77:46:F6:BD:93 |
| ~~[http://192.168.9.2/](http://192.168.9.2/)~~ | sg2 | truenas  [storage gateway netstack](https://netstack.org/docs/lan/storage/) on i3 | cf:sg  | b0:83:fe:65:80:80 |
| ~~[http://192.168.9.2:81/](http://192.168.6.9:81/)~~ | sg2 | truenas admin  [storage admin netstack](http://192.168.6.2:81) on i3 | cf:sg  | b0:83:fe:65:80:80 |
| ~~[http://192.168.9.3/](http://192.168.9.3/)~~ | cg2 | proxmox  [compute gateway netstack](https://netstack.org/docs/lan/compute/) cfPlex (win11) subnet | cg hardware (Hyper-V) | 10:C3:7B:46:0C:ED |
| res | - | - | - | na |
| ~~[http://192.168.6.4/](http://192.168.6.4/)~~ | - | - | - | 00:00:00:00:00:04 |
| ~~[http://192.168.6.5/](http://192.168.6.5/)~~ | - | - | - | 00:00:00:00:00:05 |
| ns2 | - | - | backup | na |
| [http://192.168.9.6:5000/ buadmin](http://192.168.6.6:5000/) | cfDVR-admin | cf:sg2 on ds411 synology | cf:sg2 | 00:11:32:08:c4:24 |
| [http://192.168.9.6:3000/ nsadmin](http://192.168.6.6:3000/) | cfDVR-gitea | cf:sg2 on ds411 synology | cf:sg2 | 00:11:32:08:c4:24 |
| [http://192.168.9.6:8081/](http://192.168.6.6:8081/) | cfDVR-metube | cf:sg2 on ds411 synology | cf:sg2 | 00:11:32:08:c4:24 |
| ~~[http://192.168.6.7:8006/](http://192.168.6.7:8006/)~~ local only inactive| sg2.cf.2cld.net | proxmox 8.1.4 | - | 00:00:00:00:00:xx |
| ~~[https://192.168.6.8/](https://192.168.6.8/)~~ local only inactive | bg | truenas old gh-garage | backup not running | 00:30:48:c7:82:b2 |
| ~~[https://192.168.6.9/](https://192.168.6.9/)~~ local only inactive | dg | git | vm on cg2 not running | 02:30:48:35:ea:a0 |
| [http://192.168.6.10:5000/ nsadmin](http://192.168.6.10:5000/) local only | nas | cfbu | cf | 00:11:32:12:b4:ed|
| Plex | - | - | - | na |
| ~~[https://192.168.6.3:32400/](https://192.168.6.3:32400/)~~ | plex | [cfPlex remote](https://24.149.22.11:32400) | cf:cg on cfPlex i7 win11 | 10:C3:7B:46:0C:ED |


