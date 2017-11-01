**Create the local repo**
```
[root@stf-btc-20171030-1 dfs]# sudo yum install httpd
Failed to set locale, defaulting to C
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirror.tzulo.com
 * epel: mirror.steadfast.net
 * extras: mirror.beyondhosting.net
 * updates: ftpmirror.your.org
Package httpd-2.4.6-67.el7.centos.6.x86_64 already installed and latest version
Nothing to do
```


**Verify if the Apache Server is up**
```[root@stf-btc-20171030-1 dfs]# service httpd status
Redirecting to /bin/systemctl status  httpd.service
● httpd.service - The Apache HTTP Server
   Loaded: loaded (/usr/lib/systemd/system/httpd.service; disabled; vendor preset: disabled)
   Active: active (running) since Tue 2017-10-31 14:27:12 PDT; 13s ago
     Docs: man:httpd(8)
           man:apachectl(8)
 Main PID: 20723 (httpd)
   Status: "Total requests: 0; Current requests/sec: 0; Current traffic:   0 B/sec"
   CGroup: /system.slice/httpd.service
           ├─20723 /usr/sbin/httpd -DFOREGROUND
           ├─20724 /usr/sbin/httpd -DFOREGROUND
           ├─20725 /usr/sbin/httpd -DFOREGROUND
           ├─20726 /usr/sbin/httpd -DFOREGROUND
           ├─20727 /usr/sbin/httpd -DFOREGROUND
           └─20728 /usr/sbin/httpd -DFOREGROUND

Oct 31 14:27:11 stf-btc-20171030-1.gce.cloudera.com systemd[1]: Starting The Apache HTTP Server...
Oct 31 14:27:12 stf-btc-20171030-1.gce.cloudera.com systemd[1]: Started The Apache HTTP Server.
```
**Downloading the parcels repos**
> CDH5
```
[root@stf-btc-20171030-1 parcels]# wget https://archive.cloudera.com/cdh5/parcels/5.9.3/CDH-5.9.3-1.cdh5.9.3.p0.4-el7.parcel

[root@stf-btc-20171030-1 parcels]# wget https://archive.cloudera.com/cdh5/parcels/5.9.3/CDH-5.9.3-1.cdh5.9.3.p0.4-el7.parcel.sha1

[root@stf-btc-20171030-1 ~]# sudo cp -R /tmp/parcels/cdh59/ /var/www/html/

[root@stf-btc-20171030-1 ~]# curl -I http://stf-btc-20171030-1.gce.cloudera.com:80/cdh59/
HTTP/1.1 200 OK
Date: Wed, 01 Nov 2017 05:17:35 GMT
Server: Apache/2.4.6 (CentOS) OpenSSL/1.0.2k-fips
Content-Type: text/html;charset=ISO-8859-1

```


