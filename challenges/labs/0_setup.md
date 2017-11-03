## <center> Challenge Setup

* List the cloud provider you are using

	* Platform / Cloud Provider: GCE 
	* Zone: GCE (Iowa) (Public) / gce_us-central1
	* GCE Image: Systest GCE Images: cloudera-systest-base-centos-6.9 (CentOS 6.9 Systest base image, 2058280130171328893)  
	* Instance: n1-highmem-2 (2 CPUs, 13gb RAM, $0.12/hour)
	* Nb. Machines: 5+(1) // Second edgeNode or backupServer
	* Expiration Time: 30 days

```
**Provisioned Instance List**

stf-btc-challenge-1.gce.cloudera.com	stf-btc-challenge-1	172.31.118.148	https://www.googleapis.com/compute/v1/projects/gcp-eng/zones/us-central1-f/instances/stf-btc-challenge-1		Provision Succeeded
stf-btc-challenge-2.gce.cloudera.com	stf-btc-challenge-2	172.31.118.147	https://www.googleapis.com/compute/v1/projects/gcp-eng/zones/us-central1-f/instances/stf-btc-challenge-2		Provision Succeeded
stf-btc-challenge-3.gce.cloudera.com	stf-btc-challenge-3	172.31.118.157	https://www.googleapis.com/compute/v1/projects/gcp-eng/zones/us-central1-f/instances/stf-btc-challenge-3		Provision Succeeded
stf-btc-challenge-4.gce.cloudera.com	stf-btc-challenge-4	172.31.118.158	https://www.googleapis.com/compute/v1/projects/gcp-eng/zones/us-central1-f/instances/stf-btc-challenge-4		Provision Succeeded
stf-btc-challenge-5.gce.cloudera.com	stf-btc-challenge-5	172.31.118.166	https://www.googleapis.com/compute/v1/projects/gcp-eng/zones/us-central1-f/instances/stf-btc-challenge-5		Provision Succeeded
stf-btc-challenge-6.gce.cloudera.com	stf-btc-challenge-6	172.31.118.167	https://www.googleapis.com/compute/v1/projects/gcp-eng/zones/us-central1-f/instances/stf-btc-challenge-6	
```
* List the Linux release you are using
```bash
[root@stf-btc-challenge-1 ~]# cat /etc/*release
CentOS release 6.9 (Final)
LSB_VERSION=base-4.0-amd64:base-4.0-noarch:core-4.0-amd64:core-4.0-noarch:graphics-4.0-amd64:graphics-4.0-noarch:printing-4.0-amd64:printing-4.0-noarch
CentOS release 6.9 (Final)
CentOS release 6.9 (Final)

or 
[root@stf-btc-challenge-1 ~]# uname -a
Linux stf-btc-challenge-1.gce.cloudera.com 2.6.32-696.1.1.el6.x86_64 #1 SMP Tue Apr 11 17:13:24 UTC 2017 x86_64 x86_64 x86_64 GNU/Linux
```
```bash
[root@stf-btc-challenge-1 ~]# yum repolist enabled
Failed to set locale, defaulting to C
Loaded plugins: fastestmirror, security
Loading mirror speeds from cached hostfile
epel/metalink                                                                                                                                                                        |  13 kB     00:00
 * base: repos.forethought.net
 * epel: mirror.steadfast.net
 * extras: repos.forethought.net
 * updates: mirror.fdcservers.net
base                                                                                                                                                                                 | 3.7 kB     00:00
centos-sclo-rh                                                                                                                                                                       | 2.9 kB     00:00
centos-sclo-sclo                                                                                                                                                                     | 2.9 kB     00:00
extras                                                                                                                                                                               | 3.4 kB     00:00
google-cloud-compute/signature                                                                                                                                                       |  454 B     00:00
google-cloud-compute/signature                                                                                                                                                       | 1.4 kB     00:00 ...
updates                                                                                                                                                                              | 3.4 kB     00:00
repo id                                                                               repo name                                                                                                       status
base                                                                                  CentOS-6 - Base                                                                                                  6706
centos-sclo-rh                                                                        CentOS-6 - SCLo rh                                                                                               5988
centos-sclo-sclo                                                                      CentOS-6 - SCLo sclo                                                                                              464
epel                                                                                  Extra Packages for Enterprise Linux 6 - x86_64                                                                  12446
extras                                                                                CentOS-6 - Extras                                                                                                  46
google-cloud-compute                                                                  Google Cloud Compute                                                                                                7
updates                                                                               CentOS-6 - Updates                                                                                                756
repolist: 26413
```
* Add the following Linux accounts to all nodes

To access to all the nodes, I will create an SSH loop that can access to all the nodes passwordless.

```bash
//Generate the public key
[root@stf-btc-challenge-1 ~]# ssh-keygen -q -t rsa -b 2048 -N '' -f ~/.ssh/id_rsa


//Push the Public key to authorized_keys file
[root@stf-btc-challenge-1 ~]# cat ~/.ssh/id_rsa.pub | sed 's/root\@.*/root/g' >> ~/.ssh/authorized_keys

//Verify the presence of the public key
[root@stf-btc-challenge-1 ~]# ls -lart ~/.ssh/authorized_keys
-rw------- 1 root root 768 Nov  3 09:04 /root/.ssh/authorized_keys

//Declare a list of all the nodes

[root@stf-btc-challenge-1 ~]# export list_hosts='stf-btc-challenge-1.gce.cloudera.com stf-btc-challenge-2.gce.cloudera.com stf-btc-challenge-3.gce.cloudera.com stf-btc-challenge-4.gce.cloudera.com stf-btc-challenge-5.gce.cloudera.com'
[root@stf-btc-challenge-1 ~]# echo $list_hosts
stf-btc-challenge-1.gce.cloudera.com stf-btc-challenge-2.gce.cloudera.com stf-btc-challenge-3.gce.cloudera.com stf-btc-challenge-4.gce.cloudera.com stf-btc-challenge-5.gce.cloudera.com
[root@stf-btc-challenge-1 ~]#

//Transfer the public key to the others hosts
[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do scp -o StrictHostKeyChecking=no ~/.ssh/* root@$host:~/.ssh/;
> done
authorized_keys                                                                                                                                                           100%  768     0.8KB/s   00:00
id_rsa                                                                                                                                                                    100% 1675     1.6KB/s   00:00
id_rsa.pub                                                                                                                                                                100%  423     0.4KB/s   00:00
known_hosts                                                                                                                                                               100% 2165     2.1KB/s   00:00
root@stf-btc-challenge-2.gce.cloudera.com's password:
authorized_keys                                                                                                                                                           100%  768     0.8KB/s   00:00
id_rsa                                                                                                                                                                    100% 1675     1.6KB/s   00:00
id_rsa.pub                                                                                                                                                                100%  423     0.4KB/s   00:00
known_hosts                                                                                                                                                               100% 2165     2.1KB/s   00:00
root@stf-btc-challenge-3.gce.cloudera.com's password:
authorized_keys                                                                                                                                                           100%  768     0.8KB/s   00:00
id_rsa                                                                                                                                                                    100% 1675     1.6KB/s   00:00
id_rsa.pub                                                                                                                                                                100%  423     0.4KB/s   00:00
known_hosts                                                                                                                                                               100% 2165     2.1KB/s   00:00
root@stf-btc-challenge-4.gce.cloudera.com's password:
authorized_keys                                                                                                                                                           100%  768     0.8KB/s   00:00
id_rsa                                                                                                                                                                    100% 1675     1.6KB/s   00:00
id_rsa.pub                                                                                                                                                                100%  423     0.4KB/s   00:00
known_hosts                                                                                                                                                               100% 2165     2.1KB/s   00:00
root@stf-btc-challenge-5.gce.cloudera.com's password:
authorized_keys                                                                                                                                                           100%  768     0.8KB/s   00:00
id_rsa                                                                                                                                                                    100% 1675     1.6KB/s   00:00
id_rsa.pub                                                                                                                                                                100%  423     0.4KB/s   00:00
known_hosts                                                                                                                                                               100% 2165     2.1KB/s   00:00
[root@stf-btc-challenge-1 ~]#

```

* Create the User `reilly` with a UID of `2800`
```bash
[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "sudo useradd -u 2800 reilly";
> done

[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "sudo passwd reilly";
> done
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user reilly.
passwd: all authentication tokens updated successfully.
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user reilly.
passwd: all authentication tokens updated successfully.
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user reilly.
passwd: all authentication tokens updated successfully.
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user reilly.
passwd: all authentication tokens updated successfully.
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user reilly.
passwd: all authentication tokens updated successfully.

```

* User `frankola` with a UID of `2900`
```bash
[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "sudo useradd -u 2900 frankola";
> done

[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "sudo passwd frankola"
> done;
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user frankola.
passwd: all authentication tokens updated successfully.
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user frankola.
passwd: all authentication tokens updated successfully.
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user frankola.
passwd: all authentication tokens updated successfully.
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user frankola.
passwd: all authentication tokens updated successfully.
New password: clouder@
BAD PASSWORD: it is based on a dictionary word
Retype new password: clouder@
Changing password for user frankola.
passwd: all authentication tokens updated successfully.

```


* Create the group `paloalto` and add `frankola` to it
```bash
[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "sudo groupadd paloalto";
> done



[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "sudo usermod -a -G paloalto frankola";
> done

```


* Create the group `sanfrancisco` and add `reilly` to it
```bash
[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "sudo groupadd sanfrancisco";
> done

[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "sudo usermod -a -G sanfrancisco reilly";
> done
``

* List the `/etc/passwd` entries for `reilly` and `frankola` 
```bash

[root@stf-btc-challenge-1 ~]# grep -e 'frankola' -e 'reilly' /etc/passwd --color
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
[root@stf-btc-challenge-1 ~]# clear

[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "grep -e 'frankola' -e 'reilly' /etc/passwd --color";
> done
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash

```

* List the `/etc/group` entries for `paloalto` and `sanfrancisco` 
```bash
[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "grep -e 'paloalto' -e 'sanfrancisco' /etc/group --color";
> done
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly

paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly
```
It's OK all the users are in their own groups. 
