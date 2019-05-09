# Overview

cf site buildout generics

## Basic Stack

### Infra front
- [192.168.1.1](http://192.168.1.1) SOHO router PUBLIC-IP: 24.149.26.202 (has inbound blocks)
- [192.168.1.2](http://192.168.1.2) FreeNAS root-what#time
- [192.168.1.3](http://192.168.1.3) GitLAB root-what#time
- [192.168.1.4](http://192.168.1.4) nginx (was tobe the inbound web proxy config through freenas)
- [192.168.1.9](http://192.168.1.9) HPE BladeSystem Onboard Admin (use firefox) admin-what#time

### Infra DHCP
- 192.168.1.20-199 DHCP via 192.168.1.1
- [192.168.1.72](http://192.168.1.72) Cisco Switch in HPE (DHCP) (use firefox)
- [192.168.1.40](http://192.168.1.40) ILO HPE (DHCP) (use firefox)
- [192.168.1.62](http://192.168.1.62) ILO HPE (DHCP) (use firefox)
- [192.168.1.72](http://192.168.1.72) Cisco Switch in HPE (DHCP) (use firefox)
- [192.168.1.142](http://192.168.1.142) Plex (DHCP)

### Infra back
- [192.168.1.201:8009](http://192.168.1.201:8009) ProxMox cf  (master node) root-what#time
- [192.168.1.202:8009](http://192.168.1.202:8009) ProxMox cf2 (cluster node)

## Reference docs

- [2cld-NetworkLayout](https://docs.google.com/spreadsheets/d/1fIs0hXZehy1KZmvjHQ6srktOA0otWPfx2Bo0VUg2oa4/edit?ts=5cd30e41#gid=0) via christrees@gmail.com
- [2cld-DataCenterLayout](https://docs.google.com/spreadsheets/d/1QBA9OzsOhxs5W3kwlhxLZCmulFgd5uHMqu2qgrbMdxE/edit#gid=0) via admin@2cld.net (me)
