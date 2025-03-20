# Services

## [cg2.cf2.2cld.net](https://192.168.9.3:8006/) at https://192.168.9.3:8006/

---

- cg2 notes

| ns  | Link | user |
|-----|-------------|--|
| ng2 | [192.168.9.1](http://192.168.9.1) |  ng (gw pfsense) admin - Time2Invest |
| sg2 | [192.168.9.2](http://192.168.9.2) |  sg (sg truenas) nsadmin - Time2Invest |
| cg2 | [192.168.9.3:8006](http://192.168.9.3:8006) |  cg (cg proxmox) root - Time2Invest |

- https://128bit.io/2010/07/23/fun-with-zfs-send-and-receive/
- ZFS [docs](https://docs.oracle.com/cd/E19253-01/819-5461/6n7ht6r0h/index.html) as root on cg2
- ZFS export [docs](https://docs.oracle.com/cd/E23824_01/html/821-1448/gbchy.html)
- ZFS on /MediaVolume is orig christrees NAS 4x4TB z2 local on cg2
- ZFS on /catpool is truenas grid and backup test 4x4TB z2 on sg2
- LXC mount unpriv [docs](https://pve.proxmox.com/wiki/Unprivileged_LXC_containers) or [tutorial](https://www.youtube.com/watch?v=jhal_wUjrJ4)
```text
mp0: /MediaVolume/TestStorage,mp=/media/TestStorage
# uid map: from uid 0 map 1005 uids (in the ct) to the range starting 100000 (on the host), so 0..1004 (ct) → 100000..101004 (host)
lxc.idmap = u 0 100000 1005
lxc.idmap = g 0 100000 1005
# we map 1 uid starting from uid 1005 onto 1005, so 1005 → 1005
lxc.idmap = u 1005 1005 1
lxc.idmap = g 1005 1005 1
# we map the rest of 65535 from 1006 upto 101006, so 1006..65535 → 101006..165535
lxc.idmap = u 1006 101006 64530
lxc.idmap = g 1006 101006 64530
```
- edit /etc/subuid  and /etc/subgid add:
```text
root:1005:1
```
- set chown on mount
```text
chown -R 1005:1005 /MediaVolume/TestStorage
```

| cmd | description |
|-----|-------------|
| zpool import | scan devices looking for zfs pools to import |
| zpool import -f catpool | force a pool to import if it was not exported |
| zfs list -d 1 | List zfs pool and subs down 1 level |
| zpool export catpool | export catpool to move |
| zpool export -f catpool | export catpool to force close data |
| lsblk | list all block devices |
| cat /proc/mounts | show all mount points? |
| cat /etc/fstab | show automounts |
| mount -a | run fstab automounts |

- zfs export man
- https://linuxhandbook.com/list-mounted-drives/
-

----

### 100 (docker)

---

- 100 (docker) notes

- Static IP: 192.168.9.11/24 gw 192.168.9.1
---
| local service | user | pw |
|------|------|----|
| [portainer](https://192.168.9.11:9443) | nsadmin | Time2Invest$ |
| [cockpit](https://192.168.9.11:9090) | nsadmin | Time2Invest |
| [gitea](https://192.168.9.11:3000) | nsadmin | Time2Invest |

---
| user    | uid  | gid | pw          | groups |
|---------|------|-----|-------------|-----|
| root    | 0    | 0   | Time2Invest | - |
| nsadmin | 1000 |1000 | Time2Invest | - |
| na      | 1001 |1001 | - | - |
| cat     | 1002 |1002 | Time2Invest | - |
| na      | 1003 |1003 | - | - |
| na      | 1004 |1004 | - | - |
| smbshare| 1005 |1005 | Time2Invest | - |

- https://tteck.github.io/Proxmox/#docker-lxc 
  - bash install on cg2 to create lxc 100 (docker)
- https://cockpit-project.org/running#debian
  - installed on lxc 100 (docker) 
  - TechHut Home Server [yt ref](https://youtu.be/zLFB6ulC0Fg?t=1078)
- https://github.com/JamesTurland/JimsGarage
  - Traefix Cloudflare [yt ref](https://www.youtube.com/watch?v=XH9XgiVM_z4)
  - https://github.com/JamesTurland/JimsGarage/tree/main/Traefik

---
- User cmds
```bash
    8  groupadd -g 1005 smbshare
    9  sudo groupadd -g 1005 smbshare
   10  cat /etc/group
   11  sudo useradd smbshare -u 1005 -g 1005 -m -s /bin/bash
   12  sudo usermod -a -G smbshare nsadmin
   13  cat /etc/group
   14  cd /media/TestStorage/
   15  ls
   16  ls -alu
   17  vi fromdockervm.txt
   18  exit
   19  ls -alu /media/TestStorage/
   20  usermod -aG sudo smbshare
   21  sudo usermod -aG sudo smbshare
   22  cat /etc/groups
   23  cat /etc/group
   24  cat /media/TestStorage/testfromnsadminsmbslwin11.txt
   25  ls -alu /media/TestStorage
   26  id
   27  id smbshare
   28  id cat
   29  id testsmb
   30  id root
   31  deluser --remove-home nsuser1
   32  sudo deluser --remove-home nsuser1
   33  sudo deluser --remove-home nsuser2
   34  id testsmb
   35  sudo delgroup testsmb
   36  cat /etc/group
   37  sudo useradd -u 1001 docker
   38  id docker
   39  sudo useradd -u 1001 nsdocker
   40  cat /etc/passwd
   41  sudo deluser --remove-home cat
   42  cat /etc/passwd
   43  cat /etc/group
   44  sudo useradd -u 1001 nsdocker
   45  cat /etc/group
   46  cat /etc/passwd
   47  sudo usermod --shell /bin/bash nsdocker
   48  cat /etc/passwd
   49  sudo passwd nsdocker
   50  sudo useradd -m /home/nsdocker nsdocker
   51  sudo useradd -m nsdocker
   52  sudo mkhomedir_helper nsdocker
```

