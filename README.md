[edit](https://github.com/2cld/cf/edit/master/README.md)

- [cf docs](./docs/)
  - [wf docs](./docs/wf) moving to [https://wf.2cld.net](https://wf.2cld.net)
  - [ajd docs](./docs/ajd)

## External

| [cf](https://dash.cloudflare.com/) hv url | service [zt](https://my.zerotier.com/network/d5e5fb65371eb4a4) |
|---|---|
| [https://nginx.cat9.me](https://nginx.cat9.me) | nginx [cflare](https://dash.cloudflare.com/)->[ct-hv](10.147.17.219)->[nsdockerhb](10.147.17.176)->[nginx](172.18.0.4) |
| [https://traefik-docker.cat9.me](https://traefik-docker.cat9.me) | traefik [cflare](https://dash.cloudflare.com/)->[ct-hv](10.147.17.219)->[nsdockerhb](10.147.17.176)->[traefik](172.18.0.2) |
| [https://portainer.cat9.me](https://portainer.cat9.me) | portainer [cflare](https://dash.cloudflare.com/)->[ct-hv](10.147.17.219)->[nsdockerhb](10.147.17.176)->[portainer](172.18.0.7) |
| [https://gitea.cat9.me](https://gitea.cat9.me) | gitea [cflare](https://dash.cloudflare.com/)->[ct-hv](10.147.17.219)->[nsdockerhb](10.147.17.176)->[gitea](172.18.0.6) |
| [https://netbox.cat9.me](https://netbox.cat9.me) | netbox [cflare](https://dash.cloudflare.com/)->[ct-hv](10.147.17.219)->[nsdockerhb](10.147.17.176)->[netbox](172.18.0.8) |

| [cf](https://dash.cloudflare.com/) wsl url | service [zt](https://my.zerotier.com/network/d5e5fb65371eb4a4) |
|---|---|
| [https://chat.bradnordyke.com](https://chat.bradnordyke.com) | ollama open-webui ->[cflare](https://dash.cloudflare.com/)->ct-hv-wsl-docker-owui |
| [https://rt.bradnordyke.com](https://rt.bradnordyke.com) | rust test ->[cflare](https://dash.cloudflare.com/)->ct-hv-wsl |
| [https://ssh.bradnordyke.com](https://ssh.bradnordyke.com) | ssh ->[cflare](https://dash.cloudflare.com/)->ct-hv-wsl ct gmail |
| [https://metube.bradnordyke.com](https://metube.bradnordyke.com) | metube ->[cflare](https://dash.cloudflare.com/)->sfDVR-docker ct gmail |
| [https://sg2.bradnordyke.com](https://sg2.bradnordyke.com) | sg2 ->[cflare](https://dash.cloudflare.com/)->ng->ng2-sg2 ct gmail |

| [cf](https://dash.cloudflare.com/) sg2 url | service [zt](https://my.zerotier.com/network/d5e5fb65371eb4a4) |
|---|---|
| [https://gitea.klopfenstein.org](https://gitea.klopfenstein.org) | gitea ->[cflare](https://dash.cloudflare.com/)->cfDVR-docker-gitea |
|---|---|
| ~~[https://casa.bradnordyke.com](https://casa.bradnordyke.com)~~ | casaos |
| ~~[https://test.bradnordyke.com](https://test.bradnordyke.com)~~ | homepage |
| ~~[https://fred.klopfenstein.org](https://fred.klopfenstein.org)~~ | guac |
| ~~[https://home.klopfenstein.org](https://home.klopfenstein.org)~~ | homer |


## Internal

| url | service |
|---|---|
| [http://192.168.6.30:3333/](http://192.168.6.30:3333/) | Rust Test -> ct-hv-wsl ghadmin gmail |
| [http://192.168.6.30:8080/](http://192.168.6.30:8080/) | openweb -> ct-hv-wsl-docker-owui ct gmail |
| [http://192.168.6.30:8123/](http://192.168.6.30:8123/) | homeassistant hvwsl cat What#Time |
| [https://192.168.6.30:9443/](https://192.168.6.30:9443/) | portainer hvwsl ghadmin What#Time? |
| [https://192.168.6.30:2020/](https://192.168.6.30:2020/) | ssh to hvwsl |
|---|---|
| ~~[http://192.168.6.30:3000/](http://192.168.6.30:3000/)~~ | homepage |
| ~~[http://192.168.6.30:8888/](http://192.168.6.30:8888/)~~ | guacamole |
| ~~[http://192.168.6.2:30013/](http://192.168.6.2:30013/)~~ | jellyfin |
| ~~[http://192.168.6.2:30092/](http://192.168.6.2:30092/)~~ | homer |
|---|---|
| zt cats-mac-mini | ssh trink@10.147.17.59 |
| zt cfDVR | ssh -p 2020 buadmin@10.147.17.209 |
| zt ct-wsl | ssh -p 2020 ghadmin@10.147.17.219 |
| zt px | ssh |



