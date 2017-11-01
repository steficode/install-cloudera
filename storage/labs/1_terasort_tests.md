
**Test HDFS throughput**

>Create an end-user Linux with the gitHub handle 
```

[root@stf-btc-20171030-1 ~]# sudo -u hdfs hdfs dfs -mkdir /user/sclairville

[root@stf-btc-20171030-1 ~]# sudo -u hdfs hdfs dfs -chown sclairville:sclairville /user/sclairville

[root@stf-btc-20171030-1 ~]# hdfs dfs -ls /user
Found 10 items
drwxr-xr-x   - admin       admin                0 2017-10-31 14:52 /user/admin
drwxr-xr-x   - hdfs        supergroup           0 2017-10-31 17:07 /user/hdfs
drwxrwxrwx   - mapred      hadoop               0 2017-10-31 14:10 /user/history
drwxrwxr-t   - hive        hive                 0 2017-10-31 14:11 /user/hive
drwxrwxr-x   - hue         hue                  0 2017-10-31 14:52 /user/hue
drwxrwxr-x   - impala      impala               0 2017-10-31 14:57 /user/impala
drwxrwxr-x   - oozie       oozie                0 2017-10-31 14:12 /user/oozie
drwxr-xr-x   - root        root                 0 2017-11-01 09:58 /user/root
drwxr-xr-x   - sclairville sclairville          0 2017-11-01 10:11 /user/sclairville
drwxr-x--x   - spark       spark                0 2017-10-31 14:59 /user/spark
```

**Create a 10 GB file using teragen**
```
[root@stf-btc-20171030-1 ~]# hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen 102400000 /user/sclairville/teragen10G
17/11/01 13:50:25 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 13:50:25 INFO terasort.TeraSort: Generating 102400000 using 2
17/11/01 13:50:26 INFO mapreduce.JobSubmitter: number of splits:2
17/11/01 13:50:26 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509498341243_0017
17/11/01 13:50:26 INFO impl.YarnClientImpl: Submitted application application_1509498341243_0017
17/11/01 13:50:26 INFO mapreduce.Job: The url to track the job: http://stf-btc-20171030-1.gce.cloudera.com:8088/proxy/application_1509498341243_0017/
17/11/01 13:50:26 INFO mapreduce.Job: Running job: job_1509498341243_0017
17/11/01 13:50:31 INFO mapreduce.Job: Job job_1509498341243_0017 running in uber mode : false
17/11/01 13:50:31 INFO mapreduce.Job:  map 0% reduce 0%
17/11/01 13:50:41 INFO mapreduce.Job:  map 4% reduce 0%
17/11/01 13:50:43 INFO mapreduce.Job:  map 8% reduce 0%
17/11/01 13:50:45 INFO mapreduce.Job:  map 11% reduce 0%
17/11/01 13:50:46 INFO mapreduce.Job:  map 12% reduce 0%
17/11/01 13:50:48 INFO mapreduce.Job:  map 14% reduce 0%
17/11/01 13:50:49 INFO mapreduce.Job:  map 16% reduce 0%
17/11/01 13:50:51 INFO mapreduce.Job:  map 18% reduce 0%
17/11/01 13:50:52 INFO mapreduce.Job:  map 20% reduce 0%
17/11/01 13:50:54 INFO mapreduce.Job:  map 22% reduce 0%
17/11/01 13:50:55 INFO mapreduce.Job:  map 24% reduce 0%
17/11/01 13:50:57 INFO mapreduce.Job:  map 26% reduce 0%
17/11/01 13:50:58 INFO mapreduce.Job:  map 28% reduce 0%
17/11/01 13:51:00 INFO mapreduce.Job:  map 30% reduce 0%
17/11/01 13:51:01 INFO mapreduce.Job:  map 32% reduce 0%
17/11/01 13:51:03 INFO mapreduce.Job:  map 34% reduce 0%
17/11/01 13:51:04 INFO mapreduce.Job:  map 36% reduce 0%
17/11/01 13:51:06 INFO mapreduce.Job:  map 38% reduce 0%
17/11/01 13:51:07 INFO mapreduce.Job:  map 41% reduce 0%
17/11/01 13:51:09 INFO mapreduce.Job:  map 42% reduce 0%
17/11/01 13:51:10 INFO mapreduce.Job:  map 44% reduce 0%
17/11/01 13:51:12 INFO mapreduce.Job:  map 47% reduce 0%
17/11/01 13:51:13 INFO mapreduce.Job:  map 49% reduce 0%
17/11/01 13:51:15 INFO mapreduce.Job:  map 51% reduce 0%
17/11/01 13:51:16 INFO mapreduce.Job:  map 53% reduce 0%
17/11/01 13:51:18 INFO mapreduce.Job:  map 55% reduce 0%
17/11/01 13:51:19 INFO mapreduce.Job:  map 57% reduce 0%
17/11/01 13:51:21 INFO mapreduce.Job:  map 59% reduce 0%
17/11/01 13:51:22 INFO mapreduce.Job:  map 61% reduce 0%
17/11/01 13:51:24 INFO mapreduce.Job:  map 63% reduce 0%
17/11/01 13:51:25 INFO mapreduce.Job:  map 65% reduce 0%
17/11/01 13:51:27 INFO mapreduce.Job:  map 66% reduce 0%
17/11/01 13:51:28 INFO mapreduce.Job:  map 68% reduce 0%
17/11/01 13:51:30 INFO mapreduce.Job:  map 70% reduce 0%
17/11/01 13:51:31 INFO mapreduce.Job:  map 72% reduce 0%
17/11/01 13:51:33 INFO mapreduce.Job:  map 75% reduce 0%
17/11/01 13:51:34 INFO mapreduce.Job:  map 77% reduce 0%
17/11/01 13:51:36 INFO mapreduce.Job:  map 79% reduce 0%
17/11/01 13:51:37 INFO mapreduce.Job:  map 81% reduce 0%
17/11/01 13:51:39 INFO mapreduce.Job:  map 83% reduce 0%
17/11/01 13:51:40 INFO mapreduce.Job:  map 86% reduce 0%
17/11/01 13:51:42 INFO mapreduce.Job:  map 88% reduce 0%
17/11/01 13:51:43 INFO mapreduce.Job:  map 90% reduce 0%
17/11/01 13:51:45 INFO mapreduce.Job:  map 92% reduce 0%
17/11/01 13:51:46 INFO mapreduce.Job:  map 94% reduce 0%
17/11/01 13:51:48 INFO mapreduce.Job:  map 96% reduce 0%
17/11/01 13:51:49 INFO mapreduce.Job:  map 98% reduce 0%
17/11/01 13:51:52 INFO mapreduce.Job:  map 100% reduce 0%
17/11/01 13:51:55 INFO mapreduce.Job: Job job_1509498341243_0017 completed successfully
17/11/01 13:51:55 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=250600
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=170
		HDFS: Number of bytes written=10240000000
		HDFS: Number of read operations=8
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=4
	Job Counters
		Launched map tasks=2
		Other local map tasks=2
		Total time spent by all maps in occupied slots (ms)=155016
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=155016
		Total vcore-seconds taken by all map tasks=155016
		Total megabyte-seconds taken by all map tasks=158736384
	Map-Reduce Framework
		Map input records=102400000
		Map output records=102400000
		Input split bytes=170
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=559
		CPU time spent (ms)=140700
		Physical memory (bytes) snapshot=749105152
		Virtual memory (bytes) snapshot=5555744768
		Total committed heap usage (bytes)=501743616
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=219910918972852281
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=10240000000



[root@stf-btc-20171030-1 ~]# hdfs dfs -ls /user/sclairville
Found 2 items
drwx------   - sclairville sclairville          0 2017-11-01 13:51 /user/sclairville/.staging
drwxr-xr-x   - sclairville sclairville          0 2017-11-01 13:51 /user/sclairville/teragen10G


[root@stf-btc-20171030-1 ~]# hdfs dfs -ls /user/sclairville/teragen10G
Found 3 items
-rw-r--r--   3 sclairville sclairville          0 2017-11-01 13:51 /user/sclairville/teragen10G/_SUCCESS
-rw-r--r--   3 sclairville sclairville 5120000000 2017-11-01 13:51 /user/sclairville/teragen10G/part-m-00000
-rw-r--r--   3 sclairville sclairville 5120000000 2017-11-01 13:51 /user/sclairville/teragen10G/part-m-00001

[root@stf-btc-20171030-1 ~]# hdfs dfs -du -s /user/sclairville/teragen10G  | cut -d' ' -f1,2-10 | awk '{ sum=$1 ;
> hum[1024**4]="Tb";hum[1024**3]="Gb";hum[1024**2]="Mb";hum[1024]="Kb"; for (x=1024**4; x>=1024; x/=1024){ if (sum>=x) { printf "%.2f %s \t %s\n",sum/x,hum[x],$2;break } }}'
9.54 Gb 	 30720000000
```


> Delete the 10G File 
```
[root@stf-btc-20171030-1 ~]# sudo -u hdfs hdfs dfs -rm -R -skipTrash /user/sclairville/teragen10G/
Deleted /user/sclairville/teragen10G
```

> Teragen of 10G file / Set the mappers to 4 / Use the time command

```
[root@stf-btc-20171030-1 ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -D mapred.map.tasks=4 -D dfs.block.size=33554432 102400000 /user/sclairville/teragen10G
17/11/01 13:56:47 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 13:56:48 INFO terasort.TeraSort: Generating 102400000 using 4
17/11/01 13:56:48 INFO mapreduce.JobSubmitter: number of splits:4
17/11/01 13:56:48 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/01 13:56:48 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/11/01 13:56:48 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509498341243_0018
17/11/01 13:56:48 INFO impl.YarnClientImpl: Submitted application application_1509498341243_0018
17/11/01 13:56:48 INFO mapreduce.Job: The url to track the job: http://stf-btc-20171030-1.gce.cloudera.com:8088/proxy/application_1509498341243_0018/
17/11/01 13:56:48 INFO mapreduce.Job: Running job: job_1509498341243_0018
17/11/01 13:56:53 INFO mapreduce.Job: Job job_1509498341243_0018 running in uber mode : false
17/11/01 13:56:53 INFO mapreduce.Job:  map 0% reduce 0%
17/11/01 13:57:07 INFO mapreduce.Job:  map 8% reduce 0%
17/11/01 13:57:10 INFO mapreduce.Job:  map 13% reduce 0%
17/11/01 13:57:13 INFO mapreduce.Job:  map 16% reduce 0%
17/11/01 13:57:16 INFO mapreduce.Job:  map 21% reduce 0%
17/11/01 13:57:19 INFO mapreduce.Job:  map 24% reduce 0%
17/11/01 13:57:22 INFO mapreduce.Job:  map 28% reduce 0%
17/11/01 13:57:25 INFO mapreduce.Job:  map 32% reduce 0%
17/11/01 13:57:28 INFO mapreduce.Job:  map 34% reduce 0%
17/11/01 13:57:31 INFO mapreduce.Job:  map 39% reduce 0%
17/11/01 13:57:34 INFO mapreduce.Job:  map 43% reduce 0%
17/11/01 13:57:37 INFO mapreduce.Job:  map 47% reduce 0%
17/11/01 13:57:40 INFO mapreduce.Job:  map 51% reduce 0%
17/11/01 13:57:43 INFO mapreduce.Job:  map 54% reduce 0%
17/11/01 13:57:46 INFO mapreduce.Job:  map 58% reduce 0%
17/11/01 13:57:49 INFO mapreduce.Job:  map 61% reduce 0%
17/11/01 13:57:52 INFO mapreduce.Job:  map 65% reduce 0%
17/11/01 13:57:55 INFO mapreduce.Job:  map 69% reduce 0%
17/11/01 13:57:58 INFO mapreduce.Job:  map 72% reduce 0%
17/11/01 13:58:01 INFO mapreduce.Job:  map 76% reduce 0%
17/11/01 13:58:04 INFO mapreduce.Job:  map 80% reduce 0%
17/11/01 13:58:07 INFO mapreduce.Job:  map 84% reduce 0%
17/11/01 13:58:10 INFO mapreduce.Job:  map 88% reduce 0%
17/11/01 13:58:13 INFO mapreduce.Job:  map 92% reduce 0%
17/11/01 13:58:16 INFO mapreduce.Job:  map 96% reduce 0%
17/11/01 13:58:18 INFO mapreduce.Job:  map 97% reduce 0%
17/11/01 13:58:19 INFO mapreduce.Job:  map 100% reduce 0%
17/11/01 13:58:22 INFO mapreduce.Job: Job job_1509498341243_0018 completed successfully
17/11/01 13:58:22 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=501196
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10240000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=335176
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=335176
		Total vcore-seconds taken by all map tasks=335176
		Total megabyte-seconds taken by all map tasks=343220224
	Map-Reduce Framework
		Map input records=102400000
		Map output records=102400000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1222
		CPU time spent (ms)=156710
		Physical memory (bytes) snapshot=1555136512
		Virtual memory (bytes) snapshot=11118350336
		Total committed heap usage (bytes)=1458569216
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=219910918972852281
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=10240000000

real	1m36.959s
user	0m4.781s
sys	0m0.264s
```
> Run the terasort command on this file

```

[root@stf-btc-20171030-1 ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/sclairville/teragen10G /user/sclairville/terasort10G_output
17/11/01 13:59:19 INFO terasort.TeraSort: starting
17/11/01 13:59:20 INFO input.FileInputFormat: Total input paths to process : 4
Spent 201ms computing base-splits.
Spent 12ms computing TeraScheduler splits.
Computing input splits took 213ms
Sampling 10 splits of 308
Making 4 from 100000 sampled records
Computing parititions took 1002ms
Spent 1217ms computing partitions.
17/11/01 13:59:21 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 13:59:21 INFO mapreduce.JobSubmitter: number of splits:308
17/11/01 13:59:22 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509498341243_0019
17/11/01 13:59:22 INFO impl.YarnClientImpl: Submitted application application_1509498341243_0019
17/11/01 13:59:22 INFO mapreduce.Job: The url to track the job: http://stf-btc-20171030-1.gce.cloudera.com:8088/proxy/application_1509498341243_0019/
17/11/01 13:59:22 INFO mapreduce.Job: Running job: job_1509498341243_0019
17/11/01 13:59:28 INFO mapreduce.Job: Job job_1509498341243_0019 running in uber mode : false
17/11/01 13:59:28 INFO mapreduce.Job:  map 0% reduce 0%
17/11/01 13:59:35 INFO mapreduce.Job:  map 1% reduce 0%
17/11/01 13:59:38 INFO mapreduce.Job:  map 2% reduce 0%
17/11/01 13:59:44 INFO mapreduce.Job:  map 3% reduce 0%
17/11/01 13:59:49 INFO mapreduce.Job:  map 4% reduce 0%
17/11/01 13:59:51 INFO mapreduce.Job:  map 5% reduce 0%
17/11/01 13:59:57 INFO mapreduce.Job:  map 6% reduce 0%
17/11/01 14:00:01 INFO mapreduce.Job:  map 7% reduce 0%
17/11/01 14:00:07 INFO mapreduce.Job:  map 8% reduce 0%
17/11/01 14:00:11 INFO mapreduce.Job:  map 9% reduce 0%
17/11/01 14:00:17 INFO mapreduce.Job:  map 10% reduce 0%
17/11/01 14:00:19 INFO mapreduce.Job:  map 11% reduce 0%
17/11/01 14:00:24 INFO mapreduce.Job:  map 12% reduce 0%
17/11/01 14:00:29 INFO mapreduce.Job:  map 13% reduce 0%
17/11/01 14:00:31 INFO mapreduce.Job:  map 14% reduce 0%
17/11/01 14:00:37 INFO mapreduce.Job:  map 15% reduce 0%
17/11/01 14:00:41 INFO mapreduce.Job:  map 16% reduce 0%
17/11/01 14:00:44 INFO mapreduce.Job:  map 17% reduce 0%
17/11/01 14:00:49 INFO mapreduce.Job:  map 18% reduce 0%
17/11/01 14:00:52 INFO mapreduce.Job:  map 19% reduce 0%
17/11/01 14:00:59 INFO mapreduce.Job:  map 20% reduce 0%
17/11/01 14:01:03 INFO mapreduce.Job:  map 21% reduce 0%
17/11/01 14:01:08 INFO mapreduce.Job:  map 22% reduce 0%
17/11/01 14:01:14 INFO mapreduce.Job:  map 23% reduce 0%
17/11/01 14:01:16 INFO mapreduce.Job:  map 24% reduce 0%
17/11/01 14:01:20 INFO mapreduce.Job:  map 25% reduce 0%
17/11/01 14:01:26 INFO mapreduce.Job:  map 26% reduce 0%
17/11/01 14:01:29 INFO mapreduce.Job:  map 27% reduce 0%
17/11/01 14:01:35 INFO mapreduce.Job:  map 28% reduce 0%
17/11/01 14:01:38 INFO mapreduce.Job:  map 29% reduce 0%
17/11/01 14:01:44 INFO mapreduce.Job:  map 30% reduce 0%
17/11/01 14:01:47 INFO mapreduce.Job:  map 31% reduce 0%
17/11/01 14:01:51 INFO mapreduce.Job:  map 32% reduce 0%
17/11/01 14:01:57 INFO mapreduce.Job:  map 33% reduce 0%
17/11/01 14:01:59 INFO mapreduce.Job:  map 34% reduce 0%
17/11/01 14:02:03 INFO mapreduce.Job:  map 35% reduce 0%
17/11/01 14:02:08 INFO mapreduce.Job:  map 36% reduce 0%
17/11/01 14:02:11 INFO mapreduce.Job:  map 37% reduce 0%
17/11/01 14:02:17 INFO mapreduce.Job:  map 38% reduce 0%
17/11/01 14:02:20 INFO mapreduce.Job:  map 39% reduce 0%
17/11/01 14:02:27 INFO mapreduce.Job:  map 40% reduce 0%
17/11/01 14:02:31 INFO mapreduce.Job:  map 41% reduce 0%
17/11/01 14:02:34 INFO mapreduce.Job:  map 42% reduce 0%
17/11/01 14:02:39 INFO mapreduce.Job:  map 43% reduce 0%
17/11/01 14:02:42 INFO mapreduce.Job:  map 44% reduce 0%
17/11/01 14:02:49 INFO mapreduce.Job:  map 45% reduce 0%
17/11/01 14:02:51 INFO mapreduce.Job:  map 46% reduce 0%
17/11/01 14:02:56 INFO mapreduce.Job:  map 47% reduce 0%
17/11/01 14:03:00 INFO mapreduce.Job:  map 48% reduce 0%
17/11/01 14:03:03 INFO mapreduce.Job:  map 49% reduce 0%
17/11/01 14:03:09 INFO mapreduce.Job:  map 50% reduce 0%
17/11/01 14:03:12 INFO mapreduce.Job:  map 51% reduce 0%
17/11/01 14:03:15 INFO mapreduce.Job:  map 52% reduce 0%
17/11/01 14:03:22 INFO mapreduce.Job:  map 54% reduce 0%
17/11/01 14:03:28 INFO mapreduce.Job:  map 55% reduce 0%
17/11/01 14:03:32 INFO mapreduce.Job:  map 56% reduce 0%
17/11/01 14:03:39 INFO mapreduce.Job:  map 57% reduce 0%
17/11/01 14:03:42 INFO mapreduce.Job:  map 58% reduce 0%
17/11/01 14:03:45 INFO mapreduce.Job:  map 59% reduce 0%
17/11/01 14:03:51 INFO mapreduce.Job:  map 60% reduce 0%
17/11/01 14:03:55 INFO mapreduce.Job:  map 61% reduce 0%
17/11/01 14:03:58 INFO mapreduce.Job:  map 62% reduce 0%
17/11/01 14:04:03 INFO mapreduce.Job:  map 63% reduce 0%
17/11/01 14:04:08 INFO mapreduce.Job:  map 64% reduce 0%
17/11/01 14:04:10 INFO mapreduce.Job:  map 65% reduce 0%
17/11/01 14:04:16 INFO mapreduce.Job:  map 66% reduce 0%
17/11/01 14:04:20 INFO mapreduce.Job:  map 67% reduce 0%
17/11/01 14:04:23 INFO mapreduce.Job:  map 68% reduce 0%
17/11/01 14:04:28 INFO mapreduce.Job:  map 69% reduce 0%
17/11/01 14:04:33 INFO mapreduce.Job:  map 70% reduce 0%
17/11/01 14:04:37 INFO mapreduce.Job:  map 71% reduce 0%
17/11/01 14:04:40 INFO mapreduce.Job:  map 72% reduce 0%
17/11/01 14:04:46 INFO mapreduce.Job:  map 73% reduce 0%
17/11/01 14:04:49 INFO mapreduce.Job:  map 74% reduce 0%
17/11/01 14:04:52 INFO mapreduce.Job:  map 75% reduce 0%
17/11/01 14:04:58 INFO mapreduce.Job:  map 76% reduce 0%
17/11/01 14:04:59 INFO mapreduce.Job:  map 77% reduce 0%
17/11/01 14:05:04 INFO mapreduce.Job:  map 78% reduce 0%
17/11/01 14:05:09 INFO mapreduce.Job:  map 79% reduce 0%
17/11/01 14:05:13 INFO mapreduce.Job:  map 80% reduce 0%
17/11/01 14:05:18 INFO mapreduce.Job:  map 81% reduce 0%
17/11/01 14:05:23 INFO mapreduce.Job:  map 82% reduce 0%
17/11/01 14:05:26 INFO mapreduce.Job:  map 83% reduce 0%
17/11/01 14:05:32 INFO mapreduce.Job:  map 83% reduce 2%
17/11/01 14:05:35 INFO mapreduce.Job:  map 83% reduce 3%
17/11/01 14:05:36 INFO mapreduce.Job:  map 84% reduce 6%
17/11/01 14:05:38 INFO mapreduce.Job:  map 84% reduce 8%
17/11/01 14:05:39 INFO mapreduce.Job:  map 84% reduce 9%
17/11/01 14:05:41 INFO mapreduce.Job:  map 84% reduce 11%
17/11/01 14:05:42 INFO mapreduce.Job:  map 84% reduce 12%
17/11/01 14:05:44 INFO mapreduce.Job:  map 85% reduce 14%
17/11/01 14:05:47 INFO mapreduce.Job:  map 85% reduce 15%
17/11/01 14:05:48 INFO mapreduce.Job:  map 85% reduce 16%
17/11/01 14:05:50 INFO mapreduce.Job:  map 85% reduce 17%
17/11/01 14:05:51 INFO mapreduce.Job:  map 85% reduce 18%
17/11/01 14:05:53 INFO mapreduce.Job:  map 85% reduce 20%
17/11/01 14:05:54 INFO mapreduce.Job:  map 86% reduce 20%
17/11/01 14:05:59 INFO mapreduce.Job:  map 86% reduce 22%
17/11/01 14:06:00 INFO mapreduce.Job:  map 87% reduce 22%
17/11/01 14:06:06 INFO mapreduce.Job:  map 88% reduce 22%
17/11/01 14:06:12 INFO mapreduce.Job:  map 89% reduce 22%
17/11/01 14:06:18 INFO mapreduce.Job:  map 90% reduce 22%
17/11/01 14:06:24 INFO mapreduce.Job:  map 91% reduce 22%
17/11/01 14:06:26 INFO mapreduce.Job:  map 91% reduce 23%
17/11/01 14:06:30 INFO mapreduce.Job:  map 92% reduce 23%
17/11/01 14:06:36 INFO mapreduce.Job:  map 93% reduce 23%
17/11/01 14:06:42 INFO mapreduce.Job:  map 94% reduce 23%
17/11/01 14:06:50 INFO mapreduce.Job:  map 94% reduce 24%
17/11/01 14:06:54 INFO mapreduce.Job:  map 95% reduce 24%
17/11/01 14:06:59 INFO mapreduce.Job:  map 96% reduce 24%
17/11/01 14:07:05 INFO mapreduce.Job:  map 97% reduce 24%
17/11/01 14:07:11 INFO mapreduce.Job:  map 98% reduce 24%
17/11/01 14:07:15 INFO mapreduce.Job:  map 98% reduce 25%
17/11/01 14:07:17 INFO mapreduce.Job:  map 99% reduce 25%
17/11/01 14:07:22 INFO mapreduce.Job:  map 100% reduce 25%
17/11/01 14:07:26 INFO mapreduce.Job:  map 100% reduce 42%
17/11/01 14:07:27 INFO mapreduce.Job:  map 100% reduce 50%
17/11/01 14:07:29 INFO mapreduce.Job:  map 100% reduce 51%
17/11/01 14:07:30 INFO mapreduce.Job:  map 100% reduce 52%
17/11/01 14:07:31 INFO mapreduce.Job:  map 100% reduce 54%
17/11/01 14:07:32 INFO mapreduce.Job:  map 100% reduce 55%
17/11/01 14:07:33 INFO mapreduce.Job:  map 100% reduce 56%
17/11/01 14:07:34 INFO mapreduce.Job:  map 100% reduce 57%
17/11/01 14:07:35 INFO mapreduce.Job:  map 100% reduce 59%
17/11/01 14:07:36 INFO mapreduce.Job:  map 100% reduce 60%
17/11/01 14:07:38 INFO mapreduce.Job:  map 100% reduce 61%
17/11/01 14:07:39 INFO mapreduce.Job:  map 100% reduce 62%
17/11/01 14:07:40 INFO mapreduce.Job:  map 100% reduce 63%
17/11/01 14:07:42 INFO mapreduce.Job:  map 100% reduce 64%
17/11/01 14:07:43 INFO mapreduce.Job:  map 100% reduce 65%
17/11/01 14:07:45 INFO mapreduce.Job:  map 100% reduce 66%
17/11/01 14:07:46 INFO mapreduce.Job:  map 100% reduce 67%
17/11/01 14:07:47 INFO mapreduce.Job:  map 100% reduce 68%
17/11/01 14:07:48 INFO mapreduce.Job:  map 100% reduce 70%
17/11/01 14:07:50 INFO mapreduce.Job:  map 100% reduce 71%
17/11/01 14:07:51 INFO mapreduce.Job:  map 100% reduce 73%
17/11/01 14:07:53 INFO mapreduce.Job:  map 100% reduce 74%
17/11/01 14:07:54 INFO mapreduce.Job:  map 100% reduce 76%
17/11/01 14:07:56 INFO mapreduce.Job:  map 100% reduce 77%
17/11/01 14:07:57 INFO mapreduce.Job:  map 100% reduce 79%
17/11/01 14:08:00 INFO mapreduce.Job:  map 100% reduce 80%
17/11/01 14:08:02 INFO mapreduce.Job:  map 100% reduce 81%
17/11/01 14:08:06 INFO mapreduce.Job:  map 100% reduce 82%
17/11/01 14:08:08 INFO mapreduce.Job:  map 100% reduce 90%
17/11/01 14:08:09 INFO mapreduce.Job:  map 100% reduce 91%
17/11/01 14:08:14 INFO mapreduce.Job:  map 100% reduce 92%
17/11/01 14:08:17 INFO mapreduce.Job:  map 100% reduce 93%
17/11/01 14:08:20 INFO mapreduce.Job:  map 100% reduce 94%
17/11/01 14:08:23 INFO mapreduce.Job:  map 100% reduce 95%
17/11/01 14:08:26 INFO mapreduce.Job:  map 100% reduce 96%
17/11/01 14:08:32 INFO mapreduce.Job:  map 100% reduce 97%
17/11/01 14:08:35 INFO mapreduce.Job:  map 100% reduce 98%
17/11/01 14:08:38 INFO mapreduce.Job:  map 100% reduce 99%
17/11/01 14:08:41 INFO mapreduce.Job:  map 100% reduce 100%
17/11/01 14:08:43 INFO mapreduce.Job: Job job_1509498341243_0019 completed successfully
17/11/01 14:08:43 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=4566820804
		FILE: Number of bytes written=9053447206
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10240038192
		HDFS: Number of bytes written=10240000000
		HDFS: Number of read operations=936
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters
		Launched map tasks=308
		Launched reduce tasks=4
		Data-local map tasks=307
		Rack-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=2123147
		Total time spent by all reduces in occupied slots (ms)=555400
		Total time spent by all map tasks (ms)=2123147
		Total time spent by all reduce tasks (ms)=555400
		Total vcore-seconds taken by all map tasks=2123147
		Total vcore-seconds taken by all reduce tasks=555400
		Total megabyte-seconds taken by all map tasks=2174102528
		Total megabyte-seconds taken by all reduce tasks=568729600
	Map-Reduce Framework
		Map input records=102400000
		Map output records=102400000
		Map output bytes=10444800000
		Map output materialized bytes=4447077776
		Input split bytes=38192
		Combine input records=0
		Combine output records=0
		Reduce input groups=102400000
		Reduce shuffle bytes=4447077776
		Reduce input records=102400000
		Reduce output records=102400000
		Spilled Records=204800000
		Shuffled Maps =1232
		Failed Shuffles=0
		Merged Map outputs=1232
		GC time elapsed (ms)=47379
		CPU time spent (ms)=1549750
		Physical memory (bytes) snapshot=150040420352
		Virtual memory (bytes) snapshot=867082608640
		Total committed heap usage (bytes)=151540203520
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=10240000000
	File Output Format Counters
		Bytes Written=10240000000
17/11/01 14:08:43 INFO terasort.TeraSort: done

real	9m25.527s
user	0m8.802s
sys	0m0.644s
```
