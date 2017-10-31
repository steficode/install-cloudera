**My cluster provisionned from GCE**

```
hostname					instance_name			ip
______________________________________________________________________________
stf-btc-20171030-1.gce.cloudera.com		stf-btc-20171030-1		172.31.120.135
stf-btc-20171030-2.gce.cloudera.com		stf-btc-20171030-2		172.31.120.137
stf-btc-20171030-3.gce.cloudera.com		stf-btc-20171030-3		172.31.120.138
stf-btc-20171030-4.gce.cloudera.com		stf-btc-20171030-4		172.31.120.160
stf-btc-20171030-5.gce.cloudera.com		stf-btc-20171030-5		172.31.120.161

sudo vim /etc/hosts
***##CLOUDERA INSTANCES GCE***
172.31.120.135 stf-btc-20171030-1
172.31.120.137 stf-btc-20171030-2
172.31.120.138 stf-btc-20171030-3
172.31.120.160 stf-btc-20171030-4
172.31.120.161 stf-btc-20171030-5
```

**Verify all the machines accessibles and well provisionned**
```
for host in stf-btc-20171030-1 stf-btc-20171030-2 stf-btc-20171030-3 stf-btc-20171030-4 stf-btc-20171030-5
do 
ping -c 2 $host
done
 
>> Result OK 
PING stf-btc-20171030-1 (172.31.120.135): 56 data bytes
64 bytes from 172.31.120.135: icmp_seq=0 ttl=60 time=51.962 ms
64 bytes from 172.31.120.135: icmp_seq=1 ttl=60 time=50.717 ms

--- stf-btc-20171030-1 ping statistics ---
2 packets transmitted, 2 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 50.717/51.340/51.962/0.623 ms
PING stf-btc-20171030-2 (172.31.120.137): 56 data bytes
64 bytes from 172.31.120.137: icmp_seq=0 ttl=60 time=51.158 ms
64 bytes from 172.31.120.137: icmp_seq=1 ttl=60 time=50.144 ms

--- stf-btc-20171030-2 ping statistics ---
2 packets transmitted, 2 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 50.144/50.651/51.158/0.507 ms
PING stf-btc-20171030-3 (172.31.120.138): 56 data bytes
64 bytes from 172.31.120.138: icmp_seq=0 ttl=60 time=50.851 ms
64 bytes from 172.31.120.138: icmp_seq=1 ttl=60 time=51.204 ms

--- stf-btc-20171030-3 ping statistics ---
2 packets transmitted, 2 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 50.851/51.028/51.204/0.176 ms
PING stf-btc-20171030-4 (172.31.120.160): 56 data bytes
64 bytes from 172.31.120.160: icmp_seq=0 ttl=60 time=51.318 ms
64 bytes from 172.31.120.160: icmp_seq=1 ttl=60 time=54.861 ms

--- stf-btc-20171030-4 ping statistics ---
2 packets transmitted, 2 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 51.318/53.090/54.861/1.771 ms
PING stf-btc-20171030-5 (172.31.120.161): 56 data bytes
64 bytes from 172.31.120.161: icmp_seq=0 ttl=60 time=51.551 ms
64 bytes from 172.31.120.161: icmp_seq=1 ttl=60 time=51.307 ms

--- stf-btc-20171030-5 ping statistics ---
2 packets transmitted, 2 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 51.307/51.429/51.551/0.122 ms
```

**Adjust vm.swpiness on all nodes**
> The parameter is to modify in this file : 
```
vim /etc/sysctl.conf
# System default settings live in /usr/lib/sysctl.d/00-system.conf.
# To override those settings, enter new settings here, or in an /etc/sysctl.d/<name>.conf file
#
# For more information, see sysctl.conf(5) and sysctl.d(5).
vm.swappiness = 1
```

**Verify th value for swappiness on each node**
```
[root@stf-btc-20171030-1 ~]# cat /proc/sys/vm/swappiness
0
````
**Set NOATIME**
````
N/A
````

**Show the mount attributes of the volumes**
> To verify on all nodes
```
stf-btc-20171030-1 : 
mount -ls 
[root@stf-btc-20171030-1 ~]# mount -ls
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,size=6661700k,nr_inodes=1665425,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/net_cls,net_prio type cgroup (rw,nosuid,nodev,noexec,relatime,net_prio,net_cls)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/pids type cgroup (rw,nosuid,nodev,noexec,relatime,pids)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/sda1 on / type xfs (rw,relatime,attr2,inode64,noquota) [/]
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=25,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime)
mqueue on /dev/mqueue type mqueue (rw,relatime)
tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,size=1333664k,mode=700)

```

**Verify is EXT volumes exists or XFS for example**
```
[root@stf-btc-20171030-1 ~]#  mount -ls | grep ext
[root@stf-btc-20171030-1 ~]#  mount -ls | grep xfs
/dev/sda1 on / type xfs (rw,relatime,attr2,inode64,noquota) [/]
``` 

**Disable transparent hugepage support**
```
[root@stf-btc-20171030-1 ~]# defrag_file_pathname=/sys/kernel/mm/transparent_hugepage/defrag
[root@stf-btc-20171030-1 ~]# echo $defrag_file_pathname
/sys/kernel/mm/transparent_hugepage/defrag

sudo sh -c "echo 'never' > defrag_file_pathname"

Add the following to /etc/rc.local to persist the change
echo never > defrag_file_pathname
```

**List your network interface configuration**
```
[root@stf-btc-20171030-1 network-scripts]# ls -lart /etc/sysconfig/network-scripts/ifcfg*
-rw-r--r--. 1 root root 254 Sep 16  2015 /etc/sysconfig/network-scripts/ifcfg-lo
-rw-r--r--. 1 root root 187 Oct 26  2016 /etc/sysconfig/network-scripts/ifcfg-eth0

```


**Show that forward and reverse host lookups are correctly resolved**
```
for host in stf-btc-20171030-1 stf-btc-20171030-2 stf-btc-20171030-3 stf-btc-20171030-4 stf-btc-20171030-5
do
getent hosts $host
done;

172.31.120.135  stf-btc-20171030-1.gce.cloudera.com
172.31.120.137  stf-btc-20171030-2.gce.cloudera.com
172.31.120.138  stf-btc-20171030-3.gce.cloudera.com
172.31.120.160  stf-btc-20171030-4.gce.cloudera.com
172.31.120.161  stf-btc-20171030-5.gce.cloudera.com
```

**Checking if nscd service is running on each host**
```
[root@stf-btc-20171030-1 network-scripts]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-30 13:16:10 PDT; 1h 1min ago
 Main PID: 3473 (nscd)
   CGroup: /system.slice/nscd.service
           └─3473 /usr/sbin/nscd

Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitored file `/etc/group` was moved into place, adding watch
Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitoring file `/etc/passwd` (7)
Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitoring directory `/etc` (2)
Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitoring file `/etc/group` (8)
Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitoring directory `/etc` (2)
Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitoring file `/etc/passwd` (7)
Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitoring directory `/etc` (2)
Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitoring file `/etc/group` (8)
Oct 30 13:16:11 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 monitoring directory `/etc` (2)
Oct 30 13:16:29 stf-btc-20171030-1.gce.cloudera.com nscd[3473]: 3473 checking for monitored file `/etc/netgroup': No such file or directory

```

**Checking if ntpd service is running on each host**
```
[root@stf-btc-20171030-1 network-scripts]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-30 13:15:28 PDT; 1h 2min ago
 Main PID: 1688 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─1688 /usr/sbin/ntpd -u ntp:ntp -g

Oct 30 13:15:28 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: Listen and drop on 1 v6wildcard :: UDP 123
Oct 30 13:15:28 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: Listen normally on 2 lo 127.0.0.1 UDP 123
Oct 30 13:15:28 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: Listen normally on 3 eth0 172.31.120.135 UDP 123
Oct 30 13:15:28 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: Listening on routing socket on fd #20 for interface updates
Oct 30 13:15:28 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: 0.0.0.0 c016 06 restart
Oct 30 13:15:28 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Oct 30 13:15:28 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: 0.0.0.0 c011 01 freq_not_set
Oct 30 13:15:29 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: 0.0.0.0 c614 04 freq_mode
Oct 30 13:36:16 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: 0.0.0.0 0612 02 freq_set kernel 31.752 PPM
Oct 30 13:36:16 stf-btc-20171030-1.gce.cloudera.com ntpd[1688]: 0.0.0.0 0615 05 clock_sync
```

