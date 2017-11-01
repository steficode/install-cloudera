
**Test HDFS throughput

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

**Create a 10 GB file using teragen
```

[root@stf-btc-20171030-1 ~]# sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen 102400000 /user/sclairville/teragen10G
17/11/01 12:05:53 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 12:05:54 INFO terasort.TeraSort: Generating 102400000 using 2
17/11/01 12:05:54 INFO mapreduce.JobSubmitter: number of splits:2
17/11/01 12:05:54 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509498341243_0012
17/11/01 12:05:55 INFO impl.YarnClientImpl: Submitted application application_1509498341243_0012
17/11/01 12:05:55 INFO mapreduce.Job: The url to track the job: http://stf-btc-20171030-1.gce.cloudera.com:8088/proxy/application_1509498341243_0012/
17/11/01 12:05:55 INFO mapreduce.Job: Running job: job_1509498341243_0012
17/11/01 12:06:00 INFO mapreduce.Job: Job job_1509498341243_0012 running in uber mode : false
17/11/01 12:06:00 INFO mapreduce.Job:  map 0% reduce 0%
17/11/01 12:06:12 INFO mapreduce.Job:  map 2% reduce 0%
17/11/01 12:06:13 INFO mapreduce.Job:  map 4% reduce 0%
17/11/01 12:06:15 INFO mapreduce.Job:  map 6% reduce 0%
17/11/01 12:06:16 INFO mapreduce.Job:  map 7% reduce 0%
17/11/01 12:06:18 INFO mapreduce.Job:  map 8% reduce 0%
17/11/01 12:06:19 INFO mapreduce.Job:  map 10% reduce 0%
17/11/01 12:06:21 INFO mapreduce.Job:  map 11% reduce 0%
17/11/01 12:06:22 INFO mapreduce.Job:  map 12% reduce 0%
17/11/01 12:06:24 INFO mapreduce.Job:  map 14% reduce 0%
17/11/01 12:06:25 INFO mapreduce.Job:  map 16% reduce 0%
17/11/01 12:06:27 INFO mapreduce.Job:  map 17% reduce 0%
17/11/01 12:06:28 INFO mapreduce.Job:  map 19% reduce 0%
17/11/01 12:06:30 INFO mapreduce.Job:  map 20% reduce 0%
17/11/01 12:06:31 INFO mapreduce.Job:  map 22% reduce 0%
17/11/01 12:06:33 INFO mapreduce.Job:  map 23% reduce 0%
17/11/01 12:06:34 INFO mapreduce.Job:  map 25% reduce 0%
17/11/01 12:06:36 INFO mapreduce.Job:  map 27% reduce 0%
17/11/01 12:06:37 INFO mapreduce.Job:  map 28% reduce 0%
17/11/01 12:06:39 INFO mapreduce.Job:  map 30% reduce 0%
17/11/01 12:06:40 INFO mapreduce.Job:  map 32% reduce 0%
17/11/01 12:06:42 INFO mapreduce.Job:  map 33% reduce 0%
17/11/01 12:06:43 INFO mapreduce.Job:  map 34% reduce 0%
17/11/01 12:06:45 INFO mapreduce.Job:  map 36% reduce 0%
17/11/01 12:06:46 INFO mapreduce.Job:  map 37% reduce 0%
17/11/01 12:06:48 INFO mapreduce.Job:  map 39% reduce 0%
17/11/01 12:06:49 INFO mapreduce.Job:  map 40% reduce 0%
17/11/01 12:06:51 INFO mapreduce.Job:  map 42% reduce 0%
17/11/01 12:06:52 INFO mapreduce.Job:  map 43% reduce 0%
17/11/01 12:06:54 INFO mapreduce.Job:  map 45% reduce 0%
17/11/01 12:06:55 INFO mapreduce.Job:  map 46% reduce 0%
17/11/01 12:06:57 INFO mapreduce.Job:  map 48% reduce 0%
17/11/01 12:06:58 INFO mapreduce.Job:  map 49% reduce 0%
17/11/01 12:07:00 INFO mapreduce.Job:  map 51% reduce 0%
17/11/01 12:07:01 INFO mapreduce.Job:  map 53% reduce 0%
17/11/01 12:07:03 INFO mapreduce.Job:  map 54% reduce 0%
17/11/01 12:07:04 INFO mapreduce.Job:  map 56% reduce 0%
17/11/01 12:07:06 INFO mapreduce.Job:  map 57% reduce 0%
17/11/01 12:07:07 INFO mapreduce.Job:  map 59% reduce 0%
17/11/01 12:07:09 INFO mapreduce.Job:  map 60% reduce 0%
17/11/01 12:07:10 INFO mapreduce.Job:  map 61% reduce 0%
17/11/01 12:07:12 INFO mapreduce.Job:  map 62% reduce 0%
17/11/01 12:07:15 INFO mapreduce.Job:  map 63% reduce 0%
17/11/01 12:07:16 INFO mapreduce.Job:  map 64% reduce 0%
17/11/01 12:07:18 INFO mapreduce.Job:  map 65% reduce 0%
17/11/01 12:07:25 INFO mapreduce.Job:  map 66% reduce 0%
17/11/01 12:07:36 INFO mapreduce.Job:  map 67% reduce 0%
17/11/01 12:07:42 INFO mapreduce.Job:  map 68% reduce 0%
17/11/01 12:07:45 INFO mapreduce.Job:  map 69% reduce 0%
17/11/01 12:07:51 INFO mapreduce.Job:  map 70% reduce 0%
17/11/01 12:07:58 INFO mapreduce.Job:  map 71% reduce 0%
17/11/01 12:08:07 INFO mapreduce.Job:  map 72% reduce 0%
17/11/01 12:08:16 INFO mapreduce.Job:  map 73% reduce 0%
17/11/01 12:08:22 INFO mapreduce.Job:  map 75% reduce 0%
17/11/01 12:08:30 INFO mapreduce.Job:  map 76% reduce 0%
17/11/01 12:08:40 INFO mapreduce.Job:  map 77% reduce 0%
17/11/01 12:08:44 INFO mapreduce.Job:  map 78% reduce 0%
17/11/01 12:08:47 INFO mapreduce.Job:  map 80% reduce 0%
17/11/01 12:08:49 INFO mapreduce.Job:  map 81% reduce 0%
17/11/01 12:08:52 INFO mapreduce.Job:  map 82% reduce 0%
17/11/01 12:08:58 INFO mapreduce.Job:  map 83% reduce 0%
17/11/01 12:09:05 INFO mapreduce.Job:  map 84% reduce 0%
17/11/01 12:09:08 INFO mapreduce.Job:  map 86% reduce 0%
17/11/01 12:09:10 INFO mapreduce.Job:  map 87% reduce 0%
17/11/01 12:09:11 INFO mapreduce.Job:  map 88% reduce 0%
17/11/01 12:09:16 INFO mapreduce.Job:  map 89% reduce 0%
17/11/01 12:09:23 INFO mapreduce.Job:  map 90% reduce 0%
17/11/01 12:09:31 INFO mapreduce.Job:  map 92% reduce 0%
17/11/01 12:09:34 INFO mapreduce.Job:  map 93% reduce 0%
17/11/01 12:09:35 INFO mapreduce.Job:  map 94% reduce 0%
17/11/01 12:09:43 INFO mapreduce.Job:  map 95% reduce 0%
17/11/01 12:09:50 INFO mapreduce.Job:  map 96% reduce 0%
17/11/01 12:10:01 INFO mapreduce.Job:  map 97% reduce 0%
17/11/01 12:10:07 INFO mapreduce.Job:  map 98% reduce 0%
17/11/01 12:10:09 INFO mapreduce.Job:  map 100% reduce 0%
17/11/01 12:10:10 INFO mapreduce.Job: Job job_1509498341243_0012 completed successfully
17/11/01 12:10:10 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=250516
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
		Total time spent by all maps in occupied slots (ms)=476698
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=476698
		Total vcore-seconds taken by all map tasks=476698
		Total megabyte-seconds taken by all map tasks=488138752
	Map-Reduce Framework
		Map input records=102400000
		Map output records=102400000
		Input split bytes=170
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1125
		CPU time spent (ms)=148080
		Physical memory (bytes) snapshot=539615232
		Virtual memory (bytes) snapshot=5573758976
		Total committed heap usage (bytes)=392691712
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=219910918972852281
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=10240000000




[root@stf-btc-20171030-1 ~]# hdfs dfs -ls /user/sclairville
Found 1 items
drwxr-xr-x   - hdfs sclairville          0 2017-11-01 12:01 /user/sclairville/teragen10G


[root@stf-btc-20171030-1 ~]# hdfs dfs -ls /user/sclairville/teragen10G
Found 3 items
-rw-r--r--   3 hdfs sclairville          0 2017-11-01 12:10 /user/sclairville/teragen10G/_SUCCESS
-rw-r--r--   3 hdfs sclairville 5120000000 2017-11-01 12:10 /user/sclairville/teragen10G/part-m-00000
-rw-r--r--   3 hdfs sclairville 5120000000 2017-11-01 12:09 /user/sclairville/teragen10G/part-m-00001


[root@stf-btc-20171030-1 ~]# hdfs dfs -du -s /user/sclairville/teragen10G  | cut -d' ' -f1,2-10 | awk '{ sum=$1 ;
> hum[1024**4]="Tb";hum[1024**3]="Gb";hum[1024**2]="Mb";hum[1024]="Kb"; for (x=1024**4; x>=1024; x/=1024){ if (sum>=x) { printf "%.2f %s \t %s\n",sum/x,hum[x],$2;break } }}'
9.54 Gb 	 30720000000

> Delete the 10G File 
```
[root@stf-btc-20171030-1 ~]# sudo -u hdfs hdfs dfs -rm -R -skipTrash /user/sclairville/teragen10G/
Deleted /user/sclairville/teragen10G
```

> Teragen of 10G file / Set the mappers to 4 / Use the time command

```

[root@stf-btc-20171030-1 ~]# time sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -D mapred.map.tasks=4 -D dfs.block.size=33554432 102400000 /user/sclairville/teragen10G
17/11/01 12:20:14 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 12:20:14 INFO terasort.TeraSort: Generating 102400000 using 4
17/11/01 12:20:14 INFO mapreduce.JobSubmitter: number of splits:4
17/11/01 12:20:14 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/01 12:20:14 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/11/01 12:20:15 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509498341243_0013
17/11/01 12:20:15 INFO impl.YarnClientImpl: Submitted application application_1509498341243_0013
17/11/01 12:20:15 INFO mapreduce.Job: The url to track the job: http://stf-btc-20171030-1.gce.cloudera.com:8088/proxy/application_1509498341243_0013/
17/11/01 12:20:15 INFO mapreduce.Job: Running job: job_1509498341243_0013
17/11/01 12:20:22 INFO mapreduce.Job: Job job_1509498341243_0013 running in uber mode : false
17/11/01 12:20:22 INFO mapreduce.Job:  map 0% reduce 0%
17/11/01 12:20:32 INFO mapreduce.Job:  map 3% reduce 0%
17/11/01 12:20:33 INFO mapreduce.Job:  map 6% reduce 0%
17/11/01 12:20:34 INFO mapreduce.Job:  map 8% reduce 0%
17/11/01 12:20:35 INFO mapreduce.Job:  map 11% reduce 0%
17/11/01 12:20:36 INFO mapreduce.Job:  map 13% reduce 0%
17/11/01 12:20:37 INFO mapreduce.Job:  map 14% reduce 0%
17/11/01 12:20:38 INFO mapreduce.Job:  map 16% reduce 0%
17/11/01 12:20:39 INFO mapreduce.Job:  map 17% reduce 0%
17/11/01 12:20:40 INFO mapreduce.Job:  map 18% reduce 0%
17/11/01 12:20:41 INFO mapreduce.Job:  map 20% reduce 0%
17/11/01 12:20:42 INFO mapreduce.Job:  map 21% reduce 0%
17/11/01 12:20:43 INFO mapreduce.Job:  map 22% reduce 0%
17/11/01 12:20:44 INFO mapreduce.Job:  map 24% reduce 0%
17/11/01 12:20:45 INFO mapreduce.Job:  map 26% reduce 0%
17/11/01 12:20:46 INFO mapreduce.Job:  map 27% reduce 0%
17/11/01 12:20:47 INFO mapreduce.Job:  map 29% reduce 0%
17/11/01 12:20:48 INFO mapreduce.Job:  map 30% reduce 0%
17/11/01 12:20:49 INFO mapreduce.Job:  map 31% reduce 0%
17/11/01 12:20:50 INFO mapreduce.Job:  map 33% reduce 0%
17/11/01 12:20:51 INFO mapreduce.Job:  map 34% reduce 0%
17/11/01 12:20:52 INFO mapreduce.Job:  map 35% reduce 0%
17/11/01 12:20:53 INFO mapreduce.Job:  map 37% reduce 0%
17/11/01 12:20:54 INFO mapreduce.Job:  map 38% reduce 0%
17/11/01 12:20:55 INFO mapreduce.Job:  map 39% reduce 0%
17/11/01 12:20:56 INFO mapreduce.Job:  map 41% reduce 0%
17/11/01 12:20:58 INFO mapreduce.Job:  map 42% reduce 0%
17/11/01 12:20:59 INFO mapreduce.Job:  map 43% reduce 0%
17/11/01 12:21:00 INFO mapreduce.Job:  map 45% reduce 0%
17/11/01 12:21:01 INFO mapreduce.Job:  map 46% reduce 0%
17/11/01 12:21:02 INFO mapreduce.Job:  map 47% reduce 0%
17/11/01 12:21:03 INFO mapreduce.Job:  map 50% reduce 0%
17/11/01 12:21:04 INFO mapreduce.Job:  map 51% reduce 0%
17/11/01 12:21:05 INFO mapreduce.Job:  map 52% reduce 0%
17/11/01 12:21:06 INFO mapreduce.Job:  map 54% reduce 0%
17/11/01 12:21:07 INFO mapreduce.Job:  map 55% reduce 0%
17/11/01 12:21:08 INFO mapreduce.Job:  map 56% reduce 0%
17/11/01 12:21:09 INFO mapreduce.Job:  map 58% reduce 0%
17/11/01 12:21:10 INFO mapreduce.Job:  map 59% reduce 0%
17/11/01 12:21:11 INFO mapreduce.Job:  map 60% reduce 0%
17/11/01 12:21:12 INFO mapreduce.Job:  map 62% reduce 0%
17/11/01 12:21:13 INFO mapreduce.Job:  map 63% reduce 0%
17/11/01 12:21:14 INFO mapreduce.Job:  map 64% reduce 0%
17/11/01 12:21:15 INFO mapreduce.Job:  map 66% reduce 0%
17/11/01 12:21:16 INFO mapreduce.Job:  map 67% reduce 0%
17/11/01 12:21:17 INFO mapreduce.Job:  map 68% reduce 0%
17/11/01 12:21:18 INFO mapreduce.Job:  map 70% reduce 0%
17/11/01 12:21:19 INFO mapreduce.Job:  map 71% reduce 0%
17/11/01 12:21:20 INFO mapreduce.Job:  map 72% reduce 0%
17/11/01 12:21:21 INFO mapreduce.Job:  map 74% reduce 0%
17/11/01 12:21:22 INFO mapreduce.Job:  map 75% reduce 0%
17/11/01 12:21:24 INFO mapreduce.Job:  map 77% reduce 0%
17/11/01 12:21:25 INFO mapreduce.Job:  map 78% reduce 0%
17/11/01 12:21:26 INFO mapreduce.Job:  map 79% reduce 0%
17/11/01 12:21:27 INFO mapreduce.Job:  map 81% reduce 0%
17/11/01 12:21:28 INFO mapreduce.Job:  map 82% reduce 0%
17/11/01 12:21:29 INFO mapreduce.Job:  map 83% reduce 0%
17/11/01 12:21:30 INFO mapreduce.Job:  map 85% reduce 0%
17/11/01 12:21:31 INFO mapreduce.Job:  map 86% reduce 0%
17/11/01 12:21:32 INFO mapreduce.Job:  map 87% reduce 0%
17/11/01 12:21:33 INFO mapreduce.Job:  map 89% reduce 0%
17/11/01 12:21:36 INFO mapreduce.Job:  map 90% reduce 0%
17/11/01 12:21:40 INFO mapreduce.Job:  map 91% reduce 0%
17/11/01 12:21:44 INFO mapreduce.Job:  map 92% reduce 0%
17/11/01 12:21:45 INFO mapreduce.Job:  map 93% reduce 0%
17/11/01 12:21:50 INFO mapreduce.Job:  map 94% reduce 0%
17/11/01 12:21:53 INFO mapreduce.Job:  map 95% reduce 0%
17/11/01 12:21:56 INFO mapreduce.Job:  map 96% reduce 0%
17/11/01 12:21:59 INFO mapreduce.Job:  map 97% reduce 0%
17/11/01 12:22:05 INFO mapreduce.Job:  map 98% reduce 0%
17/11/01 12:22:11 INFO mapreduce.Job:  map 99% reduce 0%
17/11/01 12:22:14 INFO mapreduce.Job:  map 100% reduce 0%
17/11/01 12:22:18 INFO mapreduce.Job: Job job_1509498341243_0013 completed successfully
17/11/01 12:22:18 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=501028
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
		Total time spent by all maps in occupied slots (ms)=387791
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=387791
		Total vcore-seconds taken by all map tasks=387791
		Total megabyte-seconds taken by all map tasks=397097984
	Map-Reduce Framework
		Map input records=102400000
		Map output records=102400000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1304
		CPU time spent (ms)=146690
		Physical memory (bytes) snapshot=1505853440
		Virtual memory (bytes) snapshot=11108139008
		Total committed heap usage (bytes)=1349517312
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=219910918972852281
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=10240000000

real	2m6.271s
user	0m4.945s
sys	0m0.349s
```
> Run the terasort command on this file

```

[root@stf-btc-20171030-1 ~]# time sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/sclairville/teragen10G /user/sclairville/terasort10G_output

[root@stf-btc-20171030-1 ~]# time sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/sclairville/teragen10G /user/sclairville/terasort10G_output
17/11/01 12:58:50 INFO terasort.TeraSort: starting
17/11/01 12:58:51 INFO input.FileInputFormat: Total input paths to process : 4
Spent 152ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 157ms
Sampling 10 splits of 308
Making 4 from 100000 sampled records
Computing parititions took 794ms
Spent 954ms computing partitions.
17/11/01 12:58:52 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-20171030-1.gce.cloudera.com/172.31.120.135:8032
17/11/01 12:58:53 INFO mapreduce.JobSubmitter: number of splits:308
17/11/01 12:58:53 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509498341243_0014
17/11/01 12:58:53 INFO impl.YarnClientImpl: Submitted application application_1509498341243_0014
17/11/01 12:58:53 INFO mapreduce.Job: The url to track the job: http://stf-btc-20171030-1.gce.cloudera.com:8088/proxy/application_1509498341243_0014/
17/11/01 12:58:53 INFO mapreduce.Job: Running job: job_1509498341243_0014
17/11/01 12:59:01 INFO mapreduce.Job: Job job_1509498341243_0014 running in uber mode : false
17/11/01 12:59:01 INFO mapreduce.Job:  map 0% reduce 0%
17/11/01 12:59:10 INFO mapreduce.Job:  map 1% reduce 0%
17/11/01 12:59:13 INFO mapreduce.Job:  map 2% reduce 0%
17/11/01 12:59:15 INFO mapreduce.Job:  map 3% reduce 0%
17/11/01 12:59:21 INFO mapreduce.Job:  map 4% reduce 0%
17/11/01 12:59:24 INFO mapreduce.Job:  map 5% reduce 0%
17/11/01 12:59:29 INFO mapreduce.Job:  map 6% reduce 0%
17/11/01 12:59:35 INFO mapreduce.Job:  map 7% reduce 0%
17/11/01 12:59:40 INFO mapreduce.Job:  map 8% reduce 0%
17/11/01 12:59:44 INFO mapreduce.Job:  map 9% reduce 0%
17/11/01 12:59:47 INFO mapreduce.Job:  map 10% reduce 0%
17/11/01 12:59:52 INFO mapreduce.Job:  map 11% reduce 0%
17/11/01 12:59:56 INFO mapreduce.Job:  map 12% reduce 0%
17/11/01 12:59:59 INFO mapreduce.Job:  map 13% reduce 0%
17/11/01 13:00:03 INFO mapreduce.Job:  map 14% reduce 0%
17/11/01 13:00:08 INFO mapreduce.Job:  map 15% reduce 0%
17/11/01 13:00:13 INFO mapreduce.Job:  map 16% reduce 0%
17/11/01 13:00:15 INFO mapreduce.Job:  map 17% reduce 0%
17/11/01 13:00:21 INFO mapreduce.Job:  map 18% reduce 0%
17/11/01 13:00:25 INFO mapreduce.Job:  map 19% reduce 0%
17/11/01 13:00:28 INFO mapreduce.Job:  map 20% reduce 0%
17/11/01 13:00:34 INFO mapreduce.Job:  map 21% reduce 0%
17/11/01 13:00:37 INFO mapreduce.Job:  map 22% reduce 0%
17/11/01 13:00:41 INFO mapreduce.Job:  map 23% reduce 0%
17/11/01 13:00:45 INFO mapreduce.Job:  map 24% reduce 0%
17/11/01 13:00:50 INFO mapreduce.Job:  map 25% reduce 0%
17/11/01 13:00:54 INFO mapreduce.Job:  map 26% reduce 0%
17/11/01 13:00:56 INFO mapreduce.Job:  map 27% reduce 0%
17/11/01 13:01:01 INFO mapreduce.Job:  map 28% reduce 0%
17/11/01 13:01:03 INFO mapreduce.Job:  map 29% reduce 0%
17/11/01 13:01:09 INFO mapreduce.Job:  map 30% reduce 0%
17/11/01 13:01:13 INFO mapreduce.Job:  map 31% reduce 0%
17/11/01 13:01:21 INFO mapreduce.Job:  map 32% reduce 0%
17/11/01 13:01:23 INFO mapreduce.Job:  map 33% reduce 0%
17/11/01 13:01:27 INFO mapreduce.Job:  map 34% reduce 0%
17/11/01 13:01:33 INFO mapreduce.Job:  map 35% reduce 0%
17/11/01 13:01:34 INFO mapreduce.Job:  map 36% reduce 0%
17/11/01 13:01:39 INFO mapreduce.Job:  map 37% reduce 0%
17/11/01 13:01:43 INFO mapreduce.Job:  map 38% reduce 0%
17/11/01 13:01:46 INFO mapreduce.Job:  map 39% reduce 0%
17/11/01 13:01:52 INFO mapreduce.Job:  map 40% reduce 0%
17/11/01 13:01:55 INFO mapreduce.Job:  map 41% reduce 0%
17/11/01 13:01:58 INFO mapreduce.Job:  map 42% reduce 0%
17/11/01 13:02:04 INFO mapreduce.Job:  map 43% reduce 0%
17/11/01 13:02:07 INFO mapreduce.Job:  map 44% reduce 0%
17/11/01 13:02:16 INFO mapreduce.Job:  map 45% reduce 0%
17/11/01 13:02:17 INFO mapreduce.Job:  map 46% reduce 0%
17/11/01 13:02:22 INFO mapreduce.Job:  map 47% reduce 0%
17/11/01 13:02:27 INFO mapreduce.Job:  map 48% reduce 0%
17/11/01 13:02:29 INFO mapreduce.Job:  map 49% reduce 0%
17/11/01 13:02:35 INFO mapreduce.Job:  map 50% reduce 0%
17/11/01 13:02:39 INFO mapreduce.Job:  map 51% reduce 0%
17/11/01 13:02:41 INFO mapreduce.Job:  map 52% reduce 0%
17/11/01 13:02:47 INFO mapreduce.Job:  map 53% reduce 0%
17/11/01 13:02:51 INFO mapreduce.Job:  map 54% reduce 0%
17/11/01 13:02:56 INFO mapreduce.Job:  map 55% reduce 0%
17/11/01 13:02:59 INFO mapreduce.Job:  map 56% reduce 0%
17/11/01 13:03:05 INFO mapreduce.Job:  map 57% reduce 0%
17/11/01 13:03:09 INFO mapreduce.Job:  map 58% reduce 0%
17/11/01 13:03:11 INFO mapreduce.Job:  map 59% reduce 0%
17/11/01 13:03:16 INFO mapreduce.Job:  map 60% reduce 0%
17/11/01 13:03:22 INFO mapreduce.Job:  map 61% reduce 0%
17/11/01 13:03:24 INFO mapreduce.Job:  map 62% reduce 0%
17/11/01 13:03:29 INFO mapreduce.Job:  map 63% reduce 0%
17/11/01 13:03:34 INFO mapreduce.Job:  map 64% reduce 0%
17/11/01 13:03:40 INFO mapreduce.Job:  map 65% reduce 0%
17/11/01 13:03:43 INFO mapreduce.Job:  map 66% reduce 0%
17/11/01 13:03:46 INFO mapreduce.Job:  map 67% reduce 0%
17/11/01 13:03:52 INFO mapreduce.Job:  map 68% reduce 0%
17/11/01 13:03:54 INFO mapreduce.Job:  map 69% reduce 0%
17/11/01 13:04:01 INFO mapreduce.Job:  map 70% reduce 0%
17/11/01 13:04:04 INFO mapreduce.Job:  map 71% reduce 0%
17/11/01 13:04:10 INFO mapreduce.Job:  map 72% reduce 0%
17/11/01 13:04:12 INFO mapreduce.Job:  map 73% reduce 0%
17/11/01 13:04:16 INFO mapreduce.Job:  map 74% reduce 0%
17/11/01 13:04:23 INFO mapreduce.Job:  map 75% reduce 0%
17/11/01 13:04:24 INFO mapreduce.Job:  map 76% reduce 0%
17/11/01 13:04:29 INFO mapreduce.Job:  map 77% reduce 0%
17/11/01 13:04:34 INFO mapreduce.Job:  map 78% reduce 0%
17/11/01 13:04:39 INFO mapreduce.Job:  map 79% reduce 0%
17/11/01 13:04:42 INFO mapreduce.Job:  map 80% reduce 0%
17/11/01 13:04:46 INFO mapreduce.Job:  map 81% reduce 0%
17/11/01 13:04:52 INFO mapreduce.Job:  map 82% reduce 0%
17/11/01 13:04:57 INFO mapreduce.Job:  map 83% reduce 0%
17/11/01 13:05:02 INFO mapreduce.Job:  map 83% reduce 3%
17/11/01 13:05:03 INFO mapreduce.Job:  map 83% reduce 6%
17/11/01 13:05:05 INFO mapreduce.Job:  map 83% reduce 9%
17/11/01 13:05:07 INFO mapreduce.Job:  map 84% reduce 9%
17/11/01 13:05:08 INFO mapreduce.Job:  map 84% reduce 12%
17/11/01 13:05:11 INFO mapreduce.Job:  map 84% reduce 13%
17/11/01 13:05:12 INFO mapreduce.Job:  map 84% reduce 14%
17/11/01 13:05:14 INFO mapreduce.Job:  map 84% reduce 16%
17/11/01 13:05:15 INFO mapreduce.Job:  map 84% reduce 17%
17/11/01 13:05:16 INFO mapreduce.Job:  map 85% reduce 17%
17/11/01 13:05:17 INFO mapreduce.Job:  map 85% reduce 18%
17/11/01 13:05:18 INFO mapreduce.Job:  map 85% reduce 19%
17/11/01 13:05:23 INFO mapreduce.Job:  map 85% reduce 20%
17/11/01 13:05:26 INFO mapreduce.Job:  map 86% reduce 21%
17/11/01 13:05:33 INFO mapreduce.Job:  map 86% reduce 22%
17/11/01 13:05:37 INFO mapreduce.Job:  map 87% reduce 22%
17/11/01 13:05:43 INFO mapreduce.Job:  map 88% reduce 22%
17/11/01 13:05:54 INFO mapreduce.Job:  map 89% reduce 22%
17/11/01 13:06:01 INFO mapreduce.Job:  map 90% reduce 22%
17/11/01 13:06:08 INFO mapreduce.Job:  map 91% reduce 22%
17/11/01 13:06:09 INFO mapreduce.Job:  map 91% reduce 23%
17/11/01 13:06:19 INFO mapreduce.Job:  map 92% reduce 23%
17/11/01 13:06:26 INFO mapreduce.Job:  map 93% reduce 23%
17/11/01 13:06:34 INFO mapreduce.Job:  map 94% reduce 23%
17/11/01 13:06:41 INFO mapreduce.Job:  map 94% reduce 24%
17/11/01 13:06:45 INFO mapreduce.Job:  map 95% reduce 24%
17/11/01 13:06:54 INFO mapreduce.Job:  map 96% reduce 24%
17/11/01 13:07:03 INFO mapreduce.Job:  map 97% reduce 24%
17/11/01 13:07:10 INFO mapreduce.Job:  map 98% reduce 24%
17/11/01 13:07:16 INFO mapreduce.Job:  map 98% reduce 25%
17/11/01 13:07:18 INFO mapreduce.Job:  map 99% reduce 25%
17/11/01 13:07:26 INFO mapreduce.Job:  map 100% reduce 25%
17/11/01 13:07:31 INFO mapreduce.Job:  map 100% reduce 39%
17/11/01 13:07:32 INFO mapreduce.Job:  map 100% reduce 48%
17/11/01 13:07:33 INFO mapreduce.Job:  map 100% reduce 50%
17/11/01 13:07:34 INFO mapreduce.Job:  map 100% reduce 53%
17/11/01 13:07:35 INFO mapreduce.Job:  map 100% reduce 54%
17/11/01 13:07:37 INFO mapreduce.Job:  map 100% reduce 57%
17/11/01 13:07:38 INFO mapreduce.Job:  map 100% reduce 58%
17/11/01 13:07:40 INFO mapreduce.Job:  map 100% reduce 60%
17/11/01 13:07:41 INFO mapreduce.Job:  map 100% reduce 61%
17/11/01 13:07:43 INFO mapreduce.Job:  map 100% reduce 62%
17/11/01 13:07:44 INFO mapreduce.Job:  map 100% reduce 63%
17/11/01 13:07:46 INFO mapreduce.Job:  map 100% reduce 66%
17/11/01 13:07:47 INFO mapreduce.Job:  map 100% reduce 67%
17/11/01 13:07:49 INFO mapreduce.Job:  map 100% reduce 68%
17/11/01 13:07:52 INFO mapreduce.Job:  map 100% reduce 71%
17/11/01 13:07:53 INFO mapreduce.Job:  map 100% reduce 72%
17/11/01 13:07:55 INFO mapreduce.Job:  map 100% reduce 74%
17/11/01 13:07:56 INFO mapreduce.Job:  map 100% reduce 75%
17/11/01 13:07:58 INFO mapreduce.Job:  map 100% reduce 77%
17/11/01 13:07:59 INFO mapreduce.Job:  map 100% reduce 78%
17/11/01 13:08:01 INFO mapreduce.Job:  map 100% reduce 79%
17/11/01 13:08:02 INFO mapreduce.Job:  map 100% reduce 80%
17/11/01 13:08:07 INFO mapreduce.Job:  map 100% reduce 89%
17/11/01 13:08:10 INFO mapreduce.Job:  map 100% reduce 90%
17/11/01 13:08:13 INFO mapreduce.Job:  map 100% reduce 91%
17/11/01 13:08:16 INFO mapreduce.Job:  map 100% reduce 92%
17/11/01 13:08:19 INFO mapreduce.Job:  map 100% reduce 93%
17/11/01 13:08:22 INFO mapreduce.Job:  map 100% reduce 94%
17/11/01 13:08:25 INFO mapreduce.Job:  map 100% reduce 95%
17/11/01 13:08:28 INFO mapreduce.Job:  map 100% reduce 96%
17/11/01 13:08:31 INFO mapreduce.Job:  map 100% reduce 97%
17/11/01 13:08:34 INFO mapreduce.Job:  map 100% reduce 98%
17/11/01 13:08:37 INFO mapreduce.Job:  map 100% reduce 99%
17/11/01 13:08:43 INFO mapreduce.Job:  map 100% reduce 100%
17/11/01 13:08:45 INFO mapreduce.Job: Job job_1509498341243_0014 completed successfully
17/11/01 13:08:45 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=4565886427
		FILE: Number of bytes written=9052501374
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
		Total time spent by all maps in occupied slots (ms)=2178605
		Total time spent by all reduces in occupied slots (ms)=663498
		Total time spent by all map tasks (ms)=2178605
		Total time spent by all reduce tasks (ms)=663498
		Total vcore-seconds taken by all map tasks=2178605
		Total vcore-seconds taken by all reduce tasks=663498
		Total megabyte-seconds taken by all map tasks=2230891520
		Total megabyte-seconds taken by all reduce tasks=679421952
	Map-Reduce Framework
		Map input records=102400000
		Map output records=102400000
		Map output bytes=10444800000
		Map output materialized bytes=4447081609
		Input split bytes=38192
		Combine input records=0
		Combine output records=0
		Reduce input groups=102400000
		Reduce shuffle bytes=4447081609
		Reduce input records=102400000
		Reduce output records=102400000
		Spilled Records=204800000
		Shuffled Maps =1232
		Failed Shuffles=0
		Merged Map outputs=1232
		GC time elapsed (ms)=44534
		CPU time spent (ms)=1528530
		Physical memory (bytes) snapshot=149083574272
		Virtual memory (bytes) snapshot=867148353536
		Total committed heap usage (bytes)=151326294016
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
17/11/01 13:08:45 INFO terasort.TeraSort: done

real	9m55.828s
user	0m8.336s
sys	0m0.616s

```
