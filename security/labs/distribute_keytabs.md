
## > Distribute the keytabs to access to all the nodes: 

```
for host in stf-btc-20171030-1 stf-btc-20171030-2 stf-btc-20171030-3 stf-btc-20171030-4 stf-btc-20171030-5;
do ssh -o StrictHostKeyChecking=no root@$host "mkdir -p /etc/security/keytabs"; 
done

[root@stf-btc-20171030-5 ~]# for host in stf-btc-20171030-1 stf-btc-20171030-2 stf-btc-20171030-3 stf-btc-20171030-4 stf-btc-20171030-5;
> do scp -o StrictHostKeyChecking=no /etc/security/keytabs/hdfs.keytab* root@$host:/etc/security/keytabs/;
> done
hdfs.keytab                                                                                                                                                               100% 3106     3.0KB/s   00:00
hdfs.keytab                                                                                                                                                               100% 3106     3.0KB/s   00:00
hdfs.keytab                                                                                                                                                               100% 3106     3.0KB/s   00:00
hdfs.keytab                                                                                                                                                               100% 3106     3.0KB/s   00:00
hdfs.keytab                                                                                                                                                               100% 3106     3.0KB/s   00:00

```

## Kinit on another node / not the server
```
[root@stf-btc-20171030-1 ~]# kinit -kt /etc/security/keytabs/hdfs.keytab hdfs/`hostname -f`
[root@stf-btc-20171030-1 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: hdfs/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM

Valid starting     Expires            Service principal
11/02/17 12:40:31  11/03/17 12:40:31  krbtgt/STEFUN.COM@STEFUN.COM
	renew until 11/09/17 11:40:31

[root@stf-btc-20171030-1 ~]# hdfs dfs -ls /
Found 4 items
drwxr-xr-x   - hdfs        supergroup           0 2017-11-01 09:36 /data
drwxr-xr-x   - sclairville sclairville          0 2017-11-02 09:00 /results
drwxrwxrwt   - hdfs        supergroup           0 2017-11-02 12:09 /tmp
drwxr-xr-x   - hdfs        supergroup           0 2017-11-01 16:26 /user

It's OK I can use the keytab ! 
```
