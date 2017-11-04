* Start the Cloudera Manager server
```bash
[root@stf-btc-challenge-2 ~]# sudo service cloudera-scm-server start
Starting cloudera-scm-server:                              [  OK  ]
```
* The first line of your CM server log
```bash
[root@stf-btc-challenge-2 ~]# head -1 /var/log/cloudera-scm-server/cloudera-scm-server.log
2017-11-03 11:41:10,839 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.13.0 (#55 built by jenkins on 20171002-1719 git: bd657e597e6743c458ee2c9aabe808b7c972981c)

```
*All lines containing the string "Started Jetty server"
```bash
[root@stf-btc-challenge-2 ~]# grep 'Started Jetty server' /var/log/cloudera-scm-server/cloudera-scm-server.log --color
2017-11-03 13:40:48,630 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
2017-11-03 21:12:09,356 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
```


