## <center> Challenge 3 - Install CDH 5.8
* Deploy Coreset services + Spark

 * Name your cluster using your GitHub handle
 change the name of the cluster to challengy.
* Set up user directories in HDFS for `reilly` and `frankola`
```bash 
[root@stf-btc-challenge-2 ~]# sudo -u hdfs hdfs dfs -mkdir /user/reilly
[root@stf-btc-challenge-2 ~]# sudo -u hdfs hdfs dfs -mkdir /user/frankola

[root@stf-btc-challenge-2 ~]# sudo -u hdfs hdfs dfs -chown frankola:frankola /user/frankola
[root@stf-btc-challenge-2 ~]# sudo -u hdfs hdfs dfs -chown reilly:reilly /user/reilly

[root@stf-btc-challenge-2 ~]# hdfs dfs -ls /user
Found 9 items
drwxr-xr-x   - admin    admin               0 2017-11-03 19:16 /user/admin
drwxr-xr-x   - frankola frankola            0 2017-11-03 21:18 /user/frankola
drwxr-xr-x   - hdfs     supergroup          0 2017-11-03 18:45 /user/hdfs
drwxrwxrwx   - mapred   hadoop              0 2017-11-03 18:23 /user/history
drwxrwxr-t   - hive     hive                0 2017-11-03 18:25 /user/hive
drwxrwxr-x   - hue      hue                 0 2017-11-03 19:15 /user/hue
drwxrwxr-x   - oozie    oozie               0 2017-11-03 18:26 /user/oozie
drwxr-xr-x   - reilly   reilly              0 2017-11-03 21:18 /user/reilly
drwxr-x--x   - spark    spark               0 2017-11-03 18:24 /user/spark
```
