**HDFS Lab: Test HDFS Snapshots**
```
export HADOOP_USER_NAME=sclairville
[root@stf-btc-20171030-1 dataset]# hdfs dfs -mkdir -p /user/sclairville/precious

[root@stf-btc-20171030-1 dataset]# wget https://data.cityofchicago.org/api/views/ijzp-q8t2/rows.csv /tmp/dataset/
--2017-11-01 14:27:11--  https://data.cityofchicago.org/api/views/ijzp-q8t2/rows.csv
Resolving data.cityofchicago.org (data.cityofchicago.org)... 52.206.140.199
Connecting to data.cityofchicago.org (data.cityofchicago.org)|52.206.140.199|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/csv]
Saving to: 'rows.csv'

    [                                                             <=>                                                                                                   ] 139,362,304  373KB/s   in 7m 36s

Last-modified header invalid -- time-stamp ignored.
2017-11-01 14:34:48 (299 KB/s) - 'rows.csv' saved [139362304]

/tmp/dataset/: Scheme missing.
FINISHED --2017-11-01 14:34:48--
Total wall clock time: 7m 37s
Downloaded: 1 files, 133M in 7m 36s (299 KB/s)


[root@stf-btc-20171030-1 dataset]# mv rows.csv rows_criminals.csv


[root@stf-btc-20171030-1 dataset]# zip rows_criminals.zip /tmp/dataset/rows_criminals.csv
  adding: tmp/dataset/rows_criminals.csv
root@stf-btc-20171030-1 dataset]# zip rows_criminals.zip /tmp/dataset/rows_criminals.csv
  adding: tmp/dataset/rows_criminals.csv (deflated 76%)

[root@stf-btc-20171030-1 dataset]# hdfs dfs -put /tmp/dataset/rows_criminals.zip /user/sclairville/precious
[root@stf-btc-20171030-1 dataset]# hdfs dfs -ls /user/sclairville/precious
Found 1 items
-rw-r--r--   3 sclairville sclairville   33610810 2017-11-01 14:43 /user/sclairville/precious/rows_criminals.zip

```

> Enable snapshots for precious

```
[root@stf-btc-20171030-1 ~]# hdfs dfs -rm -R -skipTrash /user/sclairville/precious
rm: The directory /user/sclairville/precious cannot be deleted since /user/sclairville/precious is snapshottable and already has snapshots

```
> Delete the precious file *.zip

```
[root@stf-btc-20171030-1 ~]# hdfs dfs -ls -R /user/sclairville/precious/
-rw-r--r--   3 sclairville sclairville   33610810 2017-11-01 14:43 /user/sclairville/precious/rows_criminals.zip
[root@stf-btc-20171030-1 ~]# hdfs dfs -rm -skipTrash /user/sclairville/precious/rows_criminals.zip
Deleted /user/sclairville/precious/rows_criminals.zip

[root@stf-btc-20171030-1 ~]# hdfs dfs -ls -R /user/sclairville/precious | wc -l
0

```

> Restore the file from the snapshot

```
Restore Snapshot Command
Summary
Status: Finished Context: HDFS Start Time: Nov 1, 3:53:19 PM Duration: 12.47s
Successfully restored snapshot /user/sclairville/precious/.snapshot/sebc-hdfs-test to path /user/sclairville/precious of HDFS service HDFS.
All   Failed Only   Running Only Details 
Completed 3 of 3 step(s).
Step	Context	Start Time	Duration	Actions
Copying /user/sclairville/precious/.snapshot/sebc-hdfs-test to /user/sclairville/.snapshot_sebc-hdfs-test_784990ac-4e95-4f02-a96f-8a9fc5379c3c.
 Process hdfs-copy (id=363) on host stf-btc-20171030-2.gce.cloudera.com (id=2) exited with 0 and expected 0
NameNode (stf-btc-20171030-2)
Nov 1, 3:53:19 PM	4.45s	
Moving /user/sclairville/.snapshot_sebc-hdfs-test_784990ac-4e95-4f02-a96f-8a9fc5379c3c/* to /user/sclairville/precious.
 Process hdfs-move (id=364) on host stf-btc-20171030-2.gce.cloudera.com (id=2) exited with 0 and expected 0
NameNode (stf-btc-20171030-2)
Nov 1, 3:53:23 PM	4s	
Deleting HDFS path /user/sclairville/.snapshot_sebc-hdfs-test_784990ac-4e95-4f02-a96f-8a9fc5379c3c.
 Process hdfs-delete (id=365) on host stf-btc-20171030-2.gce.cloudera.com (id=2) exited with 0 and expected 0

```

