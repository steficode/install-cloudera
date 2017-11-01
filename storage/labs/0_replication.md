**Storage Labs Steps
>Create Partner folder in my Boomerang Cluster

```
[root@stf-btc-20171030-1 ~]# sudo -u hdfs hdfs dfs -mkdir /tmp/mgregory
```
> Using Teragen to generate a 500Mb File 

```
[root@stf-btc-20171030-1 ~]# sudo -u hdfs hdfs dfs -mkdir /tmp/stefun
[root@stf-btc-20171030-1 ~]# sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen 5000000 /tmp/stefun/teragen_files

17/11/01 09:46:49 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 09:46:50 INFO terasort.TeraSort: Generating 5000000 using 2
17/11/01 09:46:50 INFO mapreduce.JobSubmitter: number of splits:2
17/11/01 09:46:50 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509498341243_0002
17/11/01 09:46:50 INFO impl.YarnClientImpl: Submitted application application_1509498341243_0002
17/11/01 09:46:50 INFO mapreduce.Job: The url to track the job: http://stf-btc-20171030-1.gce.cloudera.com:8088/proxy/application_1509498341243_0002/
17/11/01 09:46:50 INFO mapreduce.Job: Running job: job_1509498341243_0002
17/11/01 09:46:58 INFO mapreduce.Job: Job job_1509498341243_0002 running in uber mode : false
17/11/01 09:46:58 INFO mapreduce.Job:  map 0% reduce 0%
17/11/01 09:47:11 INFO mapreduce.Job:  map 78% reduce 0%
17/11/01 09:47:12 INFO mapreduce.Job:  map 87% reduce 0%
17/11/01 09:47:13 INFO mapreduce.Job:  map 100% reduce 0%
17/11/01 09:47:13 INFO mapreduce.Job: Job job_1509498341243_0002 completed successfully
17/11/01 09:47:13 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=250506
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=167
		HDFS: Number of bytes written=500000000
		HDFS: Number of read operations=8
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=4
	Job Counters
		Launched map tasks=2
		Other local map tasks=2
		Total time spent by all maps in occupied slots (ms)=24793
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=24793
		Total vcore-seconds taken by all map tasks=24793
		Total megabyte-seconds taken by all map tasks=25388032
	Map-Reduce Framework
		Map input records=5000000
		Map output records=5000000
		Input split bytes=167
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=386
		CPU time spent (ms)=11670
		Physical memory (bytes) snapshot=673550336
		Virtual memory (bytes) snapshot=5549096960
		Total committed heap usage (bytes)=681574400
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=10735710707299981
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=500000000

[root@stf-btc-20171030-1 ~]# hdfs dfs -ls -R /tmp/stefun
drwxr-xr-x   - hdfs supergroup          0 2017-11-01 09:47 /tmp/stefun/teragen_files
-rw-r--r--   3 hdfs supergroup          0 2017-11-01 09:47 /tmp/stefun/teragen_files/_SUCCESS
-rw-r--r--   3 hdfs supergroup  250000000 2017-11-01 09:47 /tmp/stefun/teragen_files/part-m-00000
-rw-r--r--   3 hdfs supergroup  250000000 2017-11-01 09:47 /tmp/stefun/teragen_files/part-m-00001

```

> DistCP to @mgregory
```

[root@stf-btc-20171030-1 ~]# sudo -u hdfs hdfs dfs -mkdir /user/root

[root@stf-btc-20171030-1 ~]# sudo -u hdfs hdfs dfs -chown root:root /user/root

[root@stf-btc-20171030-1 ~]# hadoop distcp hdfs://stf-btc-20171030-2.gce.cloudera.com/tmp/stefun/teragen_files hdfs://mgregory-sebc-1.gce.cloudera.com/data/boomerang
17/11/01 10:01:42 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, append=false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=null, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://stf-btc-20171030-2.gce.cloudera.com/tmp/stefun/teragen_files], targetPath=hdfs://mgregory-sebc-1.gce.cloudera.com/data/boomerang, targetPathExists=true, filtersFile='null'}
17/11/01 10:01:42 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 10:01:43 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 4; dirCnt = 1
17/11/01 10:01:43 INFO tools.SimpleCopyListing: Build file listing completed.
17/11/01 10:01:43 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/11/01 10:01:43 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/11/01 10:01:43 INFO tools.DistCp: Number of paths in the copy list: 4
17/11/01 10:01:43 INFO tools.DistCp: Number of paths in the copy list: 4
17/11/01 10:01:43 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 10:01:44 INFO mapreduce.JobSubmitter: number of splits:3
17/11/01 10:01:44 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509498341243_0003
17/11/01 10:01:44 INFO impl.YarnClientImpl: Submitted application application_1509498341243_0003
17/11/01 10:01:44 INFO mapreduce.Job: The url to track the job: http://stf-btc-20171030-1.gce.cloudera.com:8088/proxy/application_1509498341243_0003/
17/11/01 10:01:44 INFO tools.DistCp: DistCp job-id: job_1509498341243_0003
17/11/01 10:01:44 INFO mapreduce.Job: Running job: job_1509498341243_0003
17/11/01 10:01:50 INFO mapreduce.Job: Job job_1509498341243_0003 running in uber mode : false
17/11/01 10:01:50 INFO mapreduce.Job:  map 0% reduce 0%
17/11/01 10:01:57 INFO mapreduce.Job:  map 33% reduce 0%
17/11/01 10:01:58 INFO mapreduce.Job:  map 67% reduce 0%
17/11/01 10:02:00 INFO mapreduce.Job:  map 100% reduce 0%
17/11/01 10:02:00 INFO mapreduce.Job: Job job_1509498341243_0003 completed successfully
17/11/01 10:02:00 INFO mapreduce.Job: Counters: 33
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=385380
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=500001816
		HDFS: Number of bytes written=500000000
		HDFS: Number of read operations=57
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=13
	Job Counters
		Launched map tasks=3
		Other local map tasks=3
		Total time spent by all maps in occupied slots (ms)=19794
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=19794
		Total vcore-seconds taken by all map tasks=19794
		Total megabyte-seconds taken by all map tasks=20269056
	Map-Reduce Framework
		Map input records=4
		Map output records=0
		Input split bytes=348
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=450
		CPU time spent (ms)=7850
		Physical memory (bytes) snapshot=755290112
		Virtual memory (bytes) snapshot=8335101952
		Total committed heap usage (bytes)=819986432
	File Input Format Counters
		Bytes Read=1468
	File Output Format Counters
		Bytes Written=0
	org.apache.hadoop.tools.mapred.CopyMapper$Counter
		BYTESCOPIED=500000000
		BYTESEXPECTED=500000000
		COPY=4
```

> Let the other use BDR
```
[root@stf-btc-20171030-1 ~]# hdfs dfs -mkdir -p /tmp/bdr

see the screenshot 2_bdr_ok.png
```


> Browse the results
```
[root@stf-btc-20171030-1 ~]# hdfs fsck /tmp/stefun/teragen_files -files -blocks
Connecting to namenode via http://stf-btc-20171030-2.gce.cloudera.com:50070
FSCK started by root (auth:SIMPLE) from /172.31.120.135 for path /tmp/stefun/teragen_files at Wed Nov 01 10:05:21 PDT 2017
/tmp/stefun/teragen_files <dir>
/tmp/stefun/teragen_files/_SUCCESS 0 bytes, 0 block(s):  OK

/tmp/stefun/teragen_files/part-m-00000 250000000 bytes, 2 block(s):  OK
0. BP-1873820704-172.31.120.135-1509484142117:blk_1073744474_3650 len=134217728 Live_repl=3
1. BP-1873820704-172.31.120.135-1509484142117:blk_1073744476_3652 len=115782272 Live_repl=3

/tmp/stefun/teragen_files/part-m-00001 250000000 bytes, 2 block(s):  OK
0. BP-1873820704-172.31.120.135-1509484142117:blk_1073744475_3651 len=134217728 Live_repl=3
1. BP-1873820704-172.31.120.135-1509484142117:blk_1073744477_3653 len=115782272 Live_repl=3

Status: HEALTHY
 Total size:	500000000 B
 Total dirs:	1
 Total files:	3
 Total symlinks:		0
 Total blocks (validated):	4 (avg. block size 125000000 B)
 Minimally replicated blocks:	4 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Wed Nov 01 10:05:21 PDT 2017 in 1 milliseconds


The filesystem under path '/tmp/stefun/teragen_files' is HEALTHY

```

