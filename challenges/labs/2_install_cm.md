* Install Cloudera Manager on the second node listed in `0_setup.md`

``bash

[root@stf-btc-challenge-2 ~]# vim /etc/yum.repos.d/cloudera-manager-server
[cloudera-manager]
name = Cloudera Manager, Version 5.12.1
baseurl = https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/5.12.1/
gpgkey = https://archive.cloudera.com/redhat/cdh/RPM-GPG-KEY-cloudera
gpgcheck = 1
~

[root@stf-btc-challenge-2 ~]# python --version
Python 2.6.6
```


**Install Oracle JDK 1.8.0.131 on all hosts**

```bash
wget -c --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.rpm

[root@stf-btc-challenge-2 JDK]# export list_hosts='stf-btc-challenge-1.gce.cloudera.com stf-btc-challenge-2.gce.cloudera.com stf-btc-challenge-3.gce.cloudera.com stf-btc-challenge-4.gce.cloudera.com stf-btc-challenge-5.gce.cloudera.com'

for host in $list_hosts;
do ssh -o StrictHostKeyChecking=no root@$host "mkdir -p JDK";
done

for host in $list_hosts; do scp -o StrictHostKeyChecking=no /root/JDK/jdk-8u131-linux-x64.rpm root@$host:/root/JDK/; done

[root@stf-btc-challenge-2 JDK]# for host in $list_hosts; do scp -o StrictHostKeyChecking=no /root/JDK/jdk-8u131-linux-x64.rpm root@$host:/root/JDK/; done
jdk-8u131-linux-x64.rpm                                                                                                                                                   100%  162MB 162.1MB/s   00:01
jdk-8u131-linux-x64.rpm                                                                                                                                                   100%  162MB 162.1MB/s   00:01
jdk-8u131-linux-x64.rpm                                                                                                                                                   100%  162MB 162.1MB/s   00:00
jdk-8u131-linux-x64.rpm                                                                                                                                                   100%  162MB 162.1MB/s   00:01
jdk-8u131-linux-x64.rpm                                                                                                                                                   100%  162MB 162.1MB/s   00:01

for host in $list_hosts;
do ssh -o StrictHostKeyChecking=no root@$host "rpm -ivh /root/JDK/jdk-8u131-linux-x64.rpm";
done


[root@stf-btc-challenge-2 JDK]# for host in $list_hosts; do ssh -o StrictHostKeyChecking=no root@$host "java -version"; done
java version "1.8.0_131"
Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)
java version "1.8.0_131"
Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)
java version "1.8.0_131"
Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)
java version "1.8.0_131"
Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)
java version "1.8.0_131"
Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)
```




```bash
[root@stf-btc-challenge-2 yum.repos.d]# sudo service cloudera-scm-server start
Starting cloudera-scm-server:
``

