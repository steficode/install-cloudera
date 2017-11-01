**Install Oracle JDK 1.8.0.131 on all hosts**

```
wget -c --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.rpm

[root@stf-btc-20171030-2 ~]# rpm -ivh jdk-8u131-linux-x64.rpm
Preparing...                          ################################# [100%]
Updating / installing...
   1:jdk1.8.0_131-2000:1.8.0_131-fcs  ################################# [100%]
Unpacking JAR files...
	tools.jar...
	plugin.jar...
	javaws.jar...
	deploy.jar...
	rt.jar...
	jsse.jar...
	charsets.jar...
	localedata.jar...
```

**Verification of the Java version installed**
```
[root@stf-btc-20171030-2 ~]# java -version
java version "1.8.0_131"
Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)
[root@stf-btc-20171030-2 ~]#

```



**Download and Push the JDBC Connector on all nodes**

```
[root@stf-btc-20171030-1 mariadb_connector]# wget https://downloads.mariadb.com/Connectors/java/connector-java-2.1.2/mariadb-java-client-2.1.2.jar

```


```
sudo yum install cloudera-manager-agent cloudera-manager-daemons
```


```
[root@stf-btc-20171030-1 yum.repos.d]# sudo yum install cloudera-manager-daemons cloudera-manager-server
Failed to set locale, defaulting to C
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirror.steadfast.net
 * epel: mirror.steadfast.net
 * extras: mirror.raystedman.net
 * updates: repos.forethought.net
Resolving Dependencies
--> Running transaction check
---> Package cloudera-manager-daemons.x86_64 0:5.9.3-1.cm593.p0.6.el7 will be installed
---> Package cloudera-manager-server.x86_64 0:5.9.3-1.cm593.p0.6.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

============================================================================================================================================================================================================
 Package                                                  Arch                                   Version                                                 Repository                                    Size
============================================================================================================================================================================================================
Installing:
 cloudera-manager-daemons                                 x86_64                                 5.9.3-1.cm593.p0.6.el7                                  cloudera-cm5                                 509 M
 cloudera-manager-server                                  x86_64                                 5.9.3-1.cm593.p0.6.el7                                  cloudera-cm5                                 8.3 k

Transaction Summary
============================================================================================================================================================================================================
Install  2 Packages

Total download size: 509 M
Installed size: 659 M
Is this ok [y/d/N]: y
Downloading packages:
warning: /var/cache/yum/x86_64/7/cloudera-cm5/packages/cloudera-manager-server-5.9.3-1.cm593.p0.6.el7.x86_64.rpm: Header V4 DSA/SHA1 Signature, key ID e8f86acd: NOKEY
Public key for cloudera-manager-server-5.9.3-1.cm593.p0.6.el7.x86_64.rpm is not installed
(1/2): cloudera-manager-server-5.9.3-1.cm593.p0.6.el7.x86_64.rpm                                                                                                                     | 8.3 kB  00:00:00
(2/2): cloudera-manager-daemons-5.9.3-1.cm593.p0.6.el7.x86_64.rpm                                                                                                                    | 509 MB  00:00:20
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                        25 MB/s | 509 MB  00:00:20
Retrieving key from https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
Importing GPG key 0xE8F86ACD:
 Userid     : "Yum Maintainer <webmaster@cloudera.com>"
 Fingerprint: 5f14 d39e f068 1aca 6f04 4a43 f90c 0d8f e8f8 6acd
 From       : https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
Is this ok [y/N]: y
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
Warning: RPMDB altered outside of yum.
  Installing : cloudera-manager-daemons-5.9.3-1.cm593.p0.6.el7.x86_64                                                                                                                                   1/2
  Installing : cloudera-manager-server-5.9.3-1.cm593.p0.6.el7.x86_64                                                                                                                                    2/2
  Verifying  : cloudera-manager-daemons-5.9.3-1.cm593.p0.6.el7.x86_64                                                                                                                                   1/2
  Verifying  : cloudera-manager-server-5.9.3-1.cm593.p0.6.el7.x86_64                                                                                                                                    2/2

Installed:
  cloudera-manager-daemons.x86_64 0:5.9.3-1.cm593.p0.6.el7                                              cloudera-manager-server.x86_64 0:5.9.3-1.cm593.p0.6.el7

Complete!

```

**Verification of the Python version**
```
[root@stf-btc-20171030-1 yum.repos.d]# python --version
Python 2.7.5
```

**Install JDBC Driver**
```
[root@stf-btc-20171030-1 tmp]# wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.44.tar.gz
--2017-10-31 11:35:52--  https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.44.tar.gz
Resolving dev.mysql.com (dev.mysql.com)... 137.254.60.11
Connecting to dev.mysql.com (dev.mysql.com)|137.254.60.11|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://cdn.mysql.com//Downloads/Connector-J/mysql-connector-java-5.1.44.tar.gz [following]
--2017-10-31 11:35:53--  https://cdn.mysql.com//Downloads/Connector-J/mysql-connector-java-5.1.44.tar.gz
Resolving cdn.mysql.com (cdn.mysql.com)... 23.53.115.168
Connecting to cdn.mysql.com (cdn.mysql.com)|23.53.115.168|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3465760 (3.3M) [application/x-tar-gz]
Saving to: 'mysql-connector-java-5.1.44.tar.gz'

100%[==================================================================================================================================================================>] 3,465,760   8.16MB/s   in 0.4s

2017-10-31 11:35:53 (8.16 MB/s) - 'mysql-connector-java-5.1.44.tar.gz' saved [3465760/3465760]
```

```
[root@stf-btc-20171030-3 tmp]# tar zxvf mysql-connector-java-5.1.44.tar.gz
```


```
[root@stf-btc-20171030-1 tmp]# mkdir -p /usr/share/java/
[root@stf-btc-20171030-1 tmp]# ll /usr/share/java/
total 0
[root@stf-btc-20171030-1 tmp]# sudo cp mysql-connector-java-5.1.44/mysql-connector-java-5.1.44-bin.jar /usr/share/java/mysql-connector-java.jar
[root@stf-btc-20171030-1 tmp]# ll /usr/share/java/
total 980
-rw-r--r-- 1 root root 999635 Oct 31 11:38 mysql-connector-java.jar
```


**Start Cloudera Manager (CM) Server**
```
[root@stf-btc-20171030-1 tmp]# sudo service cloudera-scm-server start
Starting cloudera-scm-server (via systemctl):              [  OK  ]
```


**Verify that Cloudera Manager Server is started**
```
[root@stf-btc-20171030-1 cloudera-scm-server]#  ps wax | grep cloudera-scm-server
 1714 pts/0    S+     0:00 grep --color=auto cloudera-scm-server
28874 ?        Ssl    4:08 /usr/java/jdk1.8.0_131/bin/java -cp .:lib/*:/usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar -server -Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties -Dfile.encoding=UTF-8 -Dcmf.root.logger=INFO,LOGFILE -Dcmf.log.dir=/var/log/cloudera-scm-server -Dcmf.log.file=cloudera-scm-server.log -Dcmf.jetty.threshhold=WARN -Dcmf.schema.dir=/usr/share/cmf/schema -Djava.awt.headless=true -Djava.net.preferIPv4Stack=true -Dpython.home=/usr/share/cmf/python -XX:+UseConcMarkSweepGC -XX:+UseParNewGC -XX:+HeapDumpOnOutOfMemoryError -Xmx2G -XX:MaxPermSize=256m -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/tmp -XX:OnOutOfMemoryError=kill -9 %p com.cloudera.server.cmf.Main
[root@stf-btc-20171030-1 cloudera-scm-server]#
```

**Remote Parcel Repository URL**
```
5.9.3-1.cdh5.9.3.p0.4	
```
