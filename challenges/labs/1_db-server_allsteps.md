
## <center> Challenge 1: Install a MySQL server



* Install MySQL 5.5 on the first node listed in `0_setup.md`
  * Use a YUM repository to install the package

```bash
On the MySQL website, I found the link corresponding to the version 5.5.58-2

[root@stf-btc-challenge-1 ~]# wget https://dev.mysql.com/get/Downloads/MySQL-5.5/MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar
--2017-11-03 09:53:32--  https://dev.mysql.com/get/Downloads/MySQL-5.5/MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar
Resolving dev.mysql.com... 137.254.60.11
Connecting to dev.mysql.com|137.254.60.11|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://cdn.mysql.com//Downloads/MySQL-5.5/MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar [following]
--2017-11-03 09:53:33--  https://cdn.mysql.com//Downloads/MySQL-5.5/MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar
Resolving cdn.mysql.com... 23.55.41.141
Connecting to cdn.mysql.com|23.55.41.141|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 150722560 (144M) [application/x-tar]
Saving to: `MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar'

100%[==================================================================================================================================================================>] 150,722,560 18.0M/s   in 8.2s

2017-11-03 09:53:41 (17.6 MB/s) - `MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar' saved [150722560/150722560]

[root@stf-btc-challenge-1 ~]# ll
total 147192
-rw-r--r-- 1 root root 150722560 Sep 13 23:33 MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar
[root@stf-btc-challenge-1 ~]# tar -xvf MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar
MySQL-embedded-5.5.58-1.el6.x86_64.rpm
MySQL-devel-5.5.58-1.el6.x86_64.rpm
MySQL-server-5.5.58-1.el6.x86_64.rpm
MySQL-client-5.5.58-1.el6.x86_64.rpm
MySQL-shared-compat-5.5.58-1.el6.x86_64.rpm
MySQL-test-5.5.58-1.el6.x86_64.rpm
MySQL-shared-5.5.58-1.el6.x86_64.rpm
[root@stf-btc-challenge-1 ~]# ll
total 294392
-rw-r--r-- 1 root root  150722560 Sep 13 23:33 MySQL-5.5.58-1.el6.x86_64.rpm-bundle.tar
-rw-r--r-- 1 7155 31415  15138692 Sep 13 23:24 MySQL-client-5.5.58-1.el6.x86_64.rpm
-rw-r--r-- 1 7155 31415   4957676 Sep 13 23:24 MySQL-devel-5.5.58-1.el6.x86_64.rpm
-rw-r--r-- 1 7155 31415  51792172 Sep 13 23:24 MySQL-embedded-5.5.58-1.el6.x86_64.rpm
-rw-r--r-- 1 7155 31415  39977080 Sep 13 23:24 MySQL-server-5.5.58-1.el6.x86_64.rpm
-rw-r--r-- 1 7155 31415   1758916 Sep 13 23:24 MySQL-shared-5.5.58-1.el6.x86_64.rpm
-rw-r--r-- 1 7155 31415   3969736 Sep 13 23:24 MySQL-shared-compat-5.5.58-1.el6.x86_64.rpm
-rw-r--r-- 1 7155 31415  33118932 Sep 13 23:24 MySQL-test-5.5.58-1.el6.x86_64.rpm

[root@stf-btc-challenge-1 ~]# sudo rpm -Uvh MySQL-*.rpm
warning: MySQL-client-5.5.58-1.el6.x86_64.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Preparing...                ########################################### [100%]
   1:MySQL-devel            ########################################### [ 14%]
   2:MySQL-client           ########################################### [ 29%]
   3:MySQL-test             ########################################### [ 43%]
   4:MySQL-embedded         ########################################### [ 57%]
   5:MySQL-shared-compat    ########################################### [ 71%]
   6:MySQL-shared           ########################################### [ 86%]
   7:MySQL-server           ########################################### [100%]
171103  9:54:56 [Note] Ignoring --secure-file-priv value as server is running with --bootstrap.
171103  9:54:56 [Note] /usr/sbin/mysqld (mysqld 5.5.58) starting as process 25265 ...
171103  9:54:56 [Note] Ignoring --secure-file-priv value as server is running with --bootstrap.
171103  9:54:56 [Note] /usr/sbin/mysqld (mysqld 5.5.58) starting as process 25272 ...

PLEASE REMEMBER TO SET A PASSWORD FOR THE MySQL root USER !
To do so, start the server, then issue the following commands:

/usr/bin/mysqladmin -u root password 'new-password'
/usr/bin/mysqladmin -u root -h stf-btc-challenge-1.gce.cloudera.com password 'new-password'

Alternatively you can run:
/usr/bin/mysql_secure_installation

which will also give you the option of removing the test
databases and anonymous user created by default.  This is
strongly recommended for production servers.

See the manual for more instructions.

Please report any problems at http://bugs.mysql.com/

[root@stf-btc-challenge-1 ~]# mv MySQL-* MySQL5.5/
[root@stf-btc-challenge-1 ~]# ll
total 4
drwxr-xr-x 2 root root 4096 Nov  3 09:56 MySQL5.5

[root@stf-btc-challenge-1 ~]# yum repolist all | grep mysql
Failed to set locale, defaulting to C
mysql-cluster-7.5-community        MySQL Cluster 7.5 Community    disabled
mysql-cluster-7.5-community-source MySQL Cluster 7.5 Community -  disabled
mysql-cluster-7.6-community        MySQL Cluster 7.6 Community    disabled
mysql-cluster-7.6-community-source MySQL Cluster 7.6 Community -  disabled
mysql-connectors-community         MySQL Connectors Community     enabled:    42
mysql-connectors-community-source  MySQL Connectors Community - S disabled
mysql-tools-community              MySQL Tools Community          enabled:    51
mysql-tools-community-source       MySQL Tools Community - Source disabled
mysql-tools-preview                MySQL Tools Preview            disabled
mysql-tools-preview-source         MySQL Tools Preview - Source   disabled
mysql55-community                  MySQL 5.5 Community Server     disabled
mysql55-community-source           MySQL 5.5 Community Server - S disabled
mysql56-community                  MySQL 5.6 Community Server     disabled
mysql56-community-source           MySQL 5.6 Community Server - S disabled
mysql57-community                  MySQL 5.7 Community Server     enabled:   219
mysql57-community-source           MySQL 5.7 Community Server - S disabled
mysql80-community                  MySQL 8.0 Community Server     disabled
mysql80-community-source           MySQL 8.0 Community Server - S disabled

[root@stf-btc-challenge-1 ~]# sudo yum-config-manager --enable mysql55-community
Failed to set locale, defaulting to C
Loaded plugins: fastestmirror
========================================================================================= repo: mysql55-community ==========================================================================================
[mysql55-community]
bandwidth = 0
base_persistdir = /var/lib/yum/repos/x86_64/6
baseurl = http://repo.mysql.com/yum/mysql-5.5-community/el/6/x86_64/
cache = 0
cachedir = /var/cache/yum/x86_64/6/mysql55-community
cost = 1000
enabled = 1
enablegroups = True
exclude =
failovermethod = priority
ftp_disable_epsv = False
gpgcadir = /var/lib/yum/repos/x86_64/6/mysql55-community/gpgcadir
gpgcakey =
gpgcheck = True
gpgdir = /var/lib/yum/repos/x86_64/6/mysql55-community/gpgdir
gpgkey = file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
hdrdir = /var/cache/yum/x86_64/6/mysql55-community/headers
http_caching = all
includepkgs =
keepalive = True
mdpolicy = group:primary
mediaid =
metadata_expire = 21600
metalink =
mirrorlist =
mirrorlist_expire = 86400
name = MySQL 5.5 Community Server
old_base_cache_dir =
password =
persistdir = /var/lib/yum/repos/x86_64/6/mysql55-community
pkgdir = /var/cache/yum/x86_64/6/mysql55-community/packages
proxy = False
proxy_dict =
proxy_password =
proxy_username =
repo_gpgcheck = False
retries = 10
skip_if_unavailable = False
ssl_check_cert_permissions = True
sslcacert =
sslclientcert =
sslclientkey =
sslverify = True
throttle = 0
timeout = 30.0
username =

[root@stf-btc-challenge-1 ~]#  yum repolist enabled | grep mysql
mysql-connectors-community MySQL Connectors Community                        42
mysql-tools-community      MySQL Tools Community                             51
mysql55-community          MySQL 5.5 Community Server                       411

[root@stf-btc-challenge-1 ~]# sudo yum install mysql-community-server
Failed to set locale, defaulting to C
Loaded plugins: fastestmirror, replace, security
Setting up Install Process
Loading mirror speeds from cached hostfile
 * base: repos.forethought.net
 * epel: mirror.steadfast.net
 * extras: repos.forethought.net
 * updates: mirror.fdcservers.net
 * webtatic: us-east.repo.webtatic.com
Resolving Dependencies
--> Running transaction check
---> Package MySQL-server.x86_64 0:5.5.58-1.el6 will be obsoleted
---> Package mysql-community-server.x86_64 0:5.5.58-2.el6 will be obsoleting
--> Processing Dependency: mysql-community-common(x86-64) = 5.5.58-2.el6 for package: mysql-community-server-5.5.58-2.el6.x86_64
--> Processing Dependency: mysql-community-client(x86-64) >= 5.5.8 for package: mysql-community-server-5.5.58-2.el6.x86_64
--> Running transaction check
---> Package MySQL-client.x86_64 0:5.5.58-1.el6 will be obsoleted
--> Processing Dependency: MySQL-client for package: MySQL-test-5.5.58-1.el6.x86_64
---> Package mysql-community-client.x86_64 0:5.5.58-2.el6 will be obsoleting
--> Processing Dependency: mysql-community-libs(x86-64) >= 5.5.8 for package: mysql-community-client-5.5.58-2.el6.x86_64
---> Package mysql-community-common.x86_64 0:5.5.58-2.el6 will be installed
--> Running transaction check
---> Package MySQL-shared.x86_64 0:5.5.58-1.el6 will be obsoleted
---> Package MySQL-test.x86_64 0:5.5.58-1.el6 will be obsoleted
---> Package mysql-community-libs.x86_64 0:5.5.58-2.el6 will be obsoleting
---> Package mysql-community-test.x86_64 0:5.5.58-2.el6 will be obsoleting
--> Processing Dependency: perl(Time::HiRes) for package: mysql-community-test-5.5.58-2.el6.x86_64
--> Running transaction check
---> Package perl-Time-HiRes.x86_64 4:1.9721-144.el6 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

============================================================================================================================================================================================================
 Package                                                 Arch                                    Version                                           Repository                                          Size
============================================================================================================================================================================================================
Installing:
 mysql-community-client                                  x86_64                                  5.5.58-2.el6                                      mysql55-community                                   15 M
     replacing  MySQL-client.x86_64 5.5.58-1.el6
 mysql-community-libs                                    x86_64                                  5.5.58-2.el6                                      mysql55-community                                  1.7 M
     replacing  MySQL-shared.x86_64 5.5.58-1.el6
 mysql-community-server                                  x86_64                                  5.5.58-2.el6                                      mysql55-community                                   38 M
     replacing  MySQL-server.x86_64 5.5.58-1.el6
 mysql-community-test                                    x86_64                                  5.5.58-2.el6                                      mysql55-community                                   32 M
     replacing  MySQL-test.x86_64 5.5.58-1.el6
Installing for dependencies:
 mysql-community-common                                  x86_64                                  5.5.58-2.el6                                      mysql55-community                                  277 k
 perl-Time-HiRes                                         x86_64                                  4:1.9721-144.el6                                  base                                                49 k

Transaction Summary
============================================================================================================================================================================================================
Install       6 Package(s)

Total download size: 86 M
Is this ok [y/N]: y
Downloading Packages:
(1/6): mysql-community-client-5.5.58-2.el6.x86_64.rpm                                                                                                                                |  15 MB     00:00
(2/6): mysql-community-common-5.5.58-2.el6.x86_64.rpm                                                                                                                                | 277 kB     00:00
(3/6): mysql-community-libs-5.5.58-2.el6.x86_64.rpm                                                                                                                                  | 1.7 MB     00:00
(4/6): mysql-community-server-5.5.58-2.el6.x86_64.rpm                                                                                                                                |  38 MB     00:01
(5/6): mysql-community-test-5.5.58-2.el6.x86_64.rpm                                                                                                                                  |  32 MB     00:01
(6/6): perl-Time-HiRes-1.9721-144.el6.x86_64.rpm                                                                                                                                     |  49 kB     00:00
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                        20 MB/s |  86 MB     00:04
warning: rpmts_HdrFromFdno: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Retrieving key from file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
Importing GPG key 0x5072E1F5:
 Userid : MySQL Release Engineering <mysql-build@oss.oracle.com>
 Package: mysql57-community-release-el6-11.noarch (installed)
 From   : /etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
Is this ok [y/N]: y
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
Warning: RPMDB altered outside of yum.
  Installing : mysql-community-common-5.5.58-2.el6.x86_64                                                                                                                                              1/10
  Installing : mysql-community-libs-5.5.58-2.el6.x86_64                                                                                                                                                2/10
  Installing : mysql-community-client-5.5.58-2.el6.x86_64                                                                                                                                              3/10
  Installing : mysql-community-server-5.5.58-2.el6.x86_64                                                                                                                                              4/10
warning: /etc/my.cnf created as /etc/my.cnf.rpmnew
  Installing : 4:perl-Time-HiRes-1.9721-144.el6.x86_64                                                                                                                                                 5/10
  Installing : mysql-community-test-5.5.58-2.el6.x86_64                                                                                                                                                6/10
  Erasing    : MySQL-test-5.5.58-1.el6.x86_64                                                                                                                                                          7/10
  Erasing    : MySQL-client-5.5.58-1.el6.x86_64                                                                                                                                                        8/10
  Erasing    : MySQL-shared-5.5.58-1.el6.x86_64                                                                                                                                                        9/10
  Erasing    : MySQL-server-5.5.58-1.el6.x86_64                                                                                                                                                       10/10
  Verifying  : mysql-community-server-5.5.58-2.el6.x86_64                                                                                                                                              1/10
  Verifying  : mysql-community-libs-5.5.58-2.el6.x86_64                                                                                                                                                2/10
  Verifying  : 4:perl-Time-HiRes-1.9721-144.el6.x86_64                                                                                                                                                 3/10
  Verifying  : mysql-community-common-5.5.58-2.el6.x86_64                                                                                                                                              4/10
  Verifying  : mysql-community-test-5.5.58-2.el6.x86_64                                                                                                                                                5/10
  Verifying  : mysql-community-client-5.5.58-2.el6.x86_64                                                                                                                                              6/10
  Verifying  : MySQL-test-5.5.58-1.el6.x86_64                                                                                                                                                          7/10
  Verifying  : MySQL-shared-5.5.58-1.el6.x86_64                                                                                                                                                        8/10
  Verifying  : MySQL-server-5.5.58-1.el6.x86_64                                                                                                                                                        9/10
  Verifying  : MySQL-client-5.5.58-1.el6.x86_64                                                                                                                                                       10/10

Installed:
  mysql-community-client.x86_64 0:5.5.58-2.el6       mysql-community-libs.x86_64 0:5.5.58-2.el6       mysql-community-server.x86_64 0:5.5.58-2.el6       mysql-community-test.x86_64 0:5.5.58-2.el6

Dependency Installed:
  mysql-community-common.x86_64 0:5.5.58-2.el6                                                            perl-Time-HiRes.x86_64 4:1.9721-144.el6

Replaced:
  MySQL-client.x86_64 0:5.5.58-1.el6                 MySQL-server.x86_64 0:5.5.58-1.el6                 MySQL-shared.x86_64 0:5.5.58-1.el6                 MySQL-test.x86_64 0:5.5.58-1.el6

Complete!
```


* Start MySQL
```bash
[root@stf-btc-challenge-1 ~]# sudo service mysqld start
Starting mysqld:                                           [  OK  ]


[root@stf-btc-challenge-1 ~]# sudo service mysqld status
mysqld (pid  25719) is running...

[root@stf-btc-challenge-1 ~]# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 4
Server version: 5.5.58 MySQL Community Server (GPL)

Copyright (c) 2000, 2017, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>

* Security / Change the root password immediately

mysql> SET PASSWORD FOR 'root'@'localhost' = PASSWORD('cloudera123');
Query OK, 0 rows affected (0.00 sec)

```


* On all cluster nodes
  * Install the database client package and JDBC connector jar on all nodes
```bash 

[root@stf-btc-challenge-1 ~]# vim mysql55.repo

[root@stf-btc-challenge-1 ~]# cat mysql55.repo
[mysql-connectors-community]
name=MySQL Connectors Community
baseurl=http://repo.mysql.com/yum/mysql-connectors-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-tools-community]
name=MySQL Tools Community
baseurl=http://repo.mysql.com/yum/mysql-tools-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

# Enable to use MySQL 5.5
[mysql55-community]
name=MySQL 5.5 Community Server
baseurl=http://repo.mysql.com/yum/mysql-5.5-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql


[root@stf-btc-challenge-1 ~]# for host in $list_hosts; do scp -o StrictHostKeyChecking=no /root/mysql55.repo root@$host:/etc/yum.repos.d/; done
mysql55.repo                                                                                                                                                              100%  621     0.6KB/s   00:00
mysql55.repo                                                                                                                                                              100%  621     0.6KB/s   00:00
mysql55.repo                                                                                                                                                              100%  621     0.6KB/s   00:00
mysql55.repo                                                                                                                                                              100%  621     0.6KB/s   00:00
mysql55.repo

or 


for host in $list_hosts;
do ssh -o StrictHostKeyChecking=no root@$host "wget https://dev.mysql.com/get/Downloads/MySQL-5.5/MySQL-client-5.5.58-1.el6.x86_64.rpm"; 
done

for host in $list_hosts;
do ssh -o StrictHostKeyChecking=no root@$host "rpm -Uvh MySQL-client-5.5.58-1.el6.x86_64.rpm"; 
done

[root@stf-btc-challenge-1 ~]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "rpm -Uvh MySQL-client-5.5.58-1.el6.x86_64.rpm";
> done
Preparing...                ##################################################
	file /usr/bin/mysql from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
	file /usr/bin/mysql_waitpid from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
	file /usr/bin/mysqladmin from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
	file /usr/bin/mysqlbinlog from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
	file /usr/bin/mysqlcheck from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
	file /usr/bin/mysqldump from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
	file /usr/bin/mysqlimport from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
	file /usr/bin/mysqlshow from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
	file /usr/bin/mysqlslap from install of MySQL-client-5.5.58-1.el6.x86_64 conflicts with file from package mysql-community-client-5.5.58-2.el6.x86_64
warning: MySQL-client-5.5.58-1.el6.x86_64.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Preparing...                ##################################################
MySQL-client                ##################################################
warning: MySQL-client-5.5.58-1.el6.x86_64.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Preparing...                ##################################################
MySQL-client                ##################################################
warning: MySQL-client-5.5.58-1.el6.x86_64.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Preparing...                ##################################################
MySQL-client                ##################################################
warning: MySQL-client-5.5.58-1.el6.x86_64.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Preparing...                ##################################################
MySQL-client                ##################################################


**Install JDBC Driver**

[root@stf-btc-challenge-1 mysql-connector-java-5.1.44]# for host in $list_hosts;
> do ssh -o StrictHostKeyChecking=no root@$host "mv /usr/share/java/mysql-connector-java-5.1.44-bin.jar /usr/share/java/mysql-connector-java.jar";
> done
[root@stf-btc-challenge-1 mysql-connector-java-5.1.44]# ll /usr/share/java/
total 980
-rw-r--r-- 1 root root 999635 Nov  3 10:44 mysql-connector-java.jar



* Start the server and create these databases:
```
create database scm DEFAULT CHARACTER SET utf8;
grant all privileges on scm.* to 'hue'@'localhost' identified by 'scm_password';

create database rman DEFAULT CHARACTER SET utf8;
grant all privileges on rman.* to 'rman'@'localhost' identified by 'rman_password';


create database metastore DEFAULT CHARACTER SET utf8;
grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';


create database oozie default character set utf8;
grant all privileges on oozie.* to 'oozie'@'localhost' identified by 'oozie_password';


create database hue DEFAULT CHARACTER SET utf8;
grant all on hue.* to 'hue'@'%' identified by 'hue_password';


create database sentry DEFAULT CHARACTER SET utf8;
grant all on sentry.* to 'hue'@'%' identified by 'sentry_password';

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hue                |
| metastore          |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
| test               |
+--------------------+
10 rows in set (0.00 sec)
```
