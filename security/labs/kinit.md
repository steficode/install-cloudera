## > Step 7:
```
Adds the password policy to the database.
[root@stf-btc-20171030-5 ~]# kadmin.local
Authenticating as principal root/admin@STEFUN.COM with password.
kadmin.local:  addpol admin
kadmin.local:  addpol users
kadmin.local:  addpol hosts
kadmin.local:  exit
```

##> Step 8:
```
Start Kerberos using the following commands:

[root@stf-btc-20171030-5 ~]# service krb5kdc start
Redirecting to /bin/systemctl start  krb5kdc.service
[root@stf-btc-20171030-5 ~]# service kadmin start
Redirecting to /bin/systemctl start  kadmin.service
```

## > Step 9:
```
Now go to Cloudera Manager UI:
Administration > Kerberos > Enable Kerberos
Check all the boxes:


Choose the below parameters:
KDC Type: MIT KDC
KDC Server Host: stf-btc-20171030-5.gce.cloudera.com
Kerberos Security Realm: STEFUN.COM
Kerberos Encryption Types: arcfour-hmac
Manage krb5.conf through Cloudera Manager: Check the box
Maximum Renewable Life for Principals: 7 days


Choose the below parameters:
Kerberos Ticket Lifetime: 1 days
Kerberos Renewable Lifetime: 7 days
Forwardable Tickets: check the box

Provide credentials of cloudera-scm principal, which we created before
KDC Account Manager Credentials:
Username: cloudera-scm@STEFUN.COM
Password:

Generate a keytab for hdfs principal

If we want to use the keytab from the node host2, then we generate hdfs keytab for the node1 principal as below:

[root@stf-btc-20171030-5 ~]# kadmin.local
Authenticating as principal root/admin@STEFUN.COM with password.
kadmin.local:  xst -norandkey -k hdfs.keytab hdfs/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM HTTP/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
Entry for principal hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type aes256-cts-hmac-sha1-96 added to keytab WRFILE:hdfs.keytab.
Entry for principal hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type aes128-cts-hmac-sha1-96 added to keytab WRFILE:hdfs.keytab.
Entry for principal hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type des3-cbc-sha1 added to keytab WRFILE:hdfs.keytab.
Entry for principal hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type arcfour-hmac added to keytab WRFILE:hdfs.keytab.
Entry for principal hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type camellia256-cts-cmac added to keytab WRFILE:hdfs.keytab.
Entry for principal hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type camellia128-cts-cmac added to keytab WRFILE:hdfs.keytab.
Entry for principal hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type des-hmac-sha1 added to keytab WRFILE:hdfs.keytab.
Entry for principal hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type des-cbc-md5 added to keytab WRFILE:hdfs.keytab.
Entry for principal HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type aes256-cts-hmac-sha1-96 added to keytab WRFILE:hdfs.keytab.
Entry for principal HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type aes128-cts-hmac-sha1-96 added to keytab WRFILE:hdfs.keytab.
Entry for principal HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type des3-cbc-sha1 added to keytab WRFILE:hdfs.keytab.
Entry for principal HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type arcfour-hmac added to keytab WRFILE:hdfs.keytab.
Entry for principal HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type camellia256-cts-cmac added to keytab WRFILE:hdfs.keytab.
Entry for principal HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type camellia128-cts-cmac added to keytab WRFILE:hdfs.keytab.
Entry for principal HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type des-hmac-sha1 added to keytab WRFILE:hdfs.keytab.
Entry for principal HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM with kvno 2, encryption type des-cbc-md5 added to keytab WRFILE:hdfs.keytab.
kadmin.local:  exit

////
(OR)
kadmin.local: addprinc hdfs@STEFUN.COM
kadmin.local: exit
////
```
## kinit  sclairville@STEFUN.COM

```
[root@stf-btc-20171030-5 ~]# kinit sclairville
Password for sclairville@STEFUN.COM:
[root@stf-btc-20171030-5 ~]#

[root@stf-btc-20171030-5 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: sclairville@STEFUN.COM

Valid starting     Expires            Service principal
11/02/17 12:28:19  11/03/17 12:28:19  krbtgt/STEFUN.COM@STEFUN.COM
	renew until 11/09/17 11:28:19
```

## To list all principals:
```
kadmin.local:  getprincs
HTTP/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
HTTP/stf-btc-20171030-2.gce.cloudera.com@STEFUN.COM
HTTP/stf-btc-20171030-3.gce.cloudera.com@STEFUN.COM
HTTP/stf-btc-20171030-4.gce.cloudera.com@STEFUN.COM
HTTP/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM
K/M@STEFUN.COM
cloudera-scm@STEFUN.COM
hdfs/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
hdfs/stf-btc-20171030-2.gce.cloudera.com@STEFUN.COM
hdfs/stf-btc-20171030-3.gce.cloudera.com@STEFUN.COM
hdfs/stf-btc-20171030-4.gce.cloudera.com@STEFUN.COM
hdfs/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM
hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
hive/stf-btc-20171030-3.gce.cloudera.com@STEFUN.COM
httpfs/stf-btc-20171030-4.gce.cloudera.com@STEFUN.COM
hue/stf-btc-20171030-4.gce.cloudera.com@STEFUN.COM
hue/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM
kadmin/admin@STEFUN.COM
kadmin/changepw@STEFUN.COM
kadmin/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM
kiprop/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM
krbtgt/STEFUN.COM@STEFUN.COM
mapred/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
oozie/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
**sclairville@STEFUN.COM**
yarn/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
yarn/stf-btc-20171030-2.gce.cloudera.com@STEFUN.COM
yarn/stf-btc-20171030-3.gce.cloudera.com@STEFUN.COM
yarn/stf-btc-20171030-4.gce.cloudera.com@STEFUN.COM
yarn/stf-btc-20171030-5.gce.cloudera.com@STEFUN.COM
zookeeper/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
zookeeper/stf-btc-20171030-2.gce.cloudera.com@STEFUN.COM
zookeeper/stf-btc-20171030-3.gce.cloudera.com@STEFUN.COM
```
