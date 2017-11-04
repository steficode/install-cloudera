## <center> Challenge 4 - HDFS Testing

* As user `reilly`, use `teragen` to generate a 65,536,000-record dataset
```bash 
[root@stf-btc-challenge-2 ~]# su - reilly
[reilly@stf-btc-challenge-2 ~]$ whoami
reilly

* Write the output to 12 files 
  * Set the block size to 32 MB
  * Set the mapper container size to 1 GiB
  * Name the target directory `tgen`
  * Use the `time` command to capture the job's duration

[reilly@stf-btc-challenge-2 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -D mapred.map.tasks=12 -D dfs.block.size=33554432 65536000 /user/reilly/teragen
17/11/03 21:37:55 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-challenge-1.gce.cloudera.com/172.31.118.148:8032
17/11/03 21:37:56 INFO terasort.TeraSort: Generating 65536000 using 12
17/11/03 21:37:56 INFO mapreduce.JobSubmitter: number of splits:12
17/11/03 21:37:56 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/03 21:37:56 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/11/03 21:37:57 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509761346450_0004
17/11/03 21:37:57 INFO impl.YarnClientImpl: Submitted application application_1509761346450_0004
17/11/03 21:37:57 INFO mapreduce.Job: The url to track the job: http://stf-btc-challenge-1.gce.cloudera.com:8088/proxy/application_1509761346450_0004/
17/11/03 21:37:57 INFO mapreduce.Job: Running job: job_1509761346450_0004
17/11/03 21:38:04 INFO mapreduce.Job: Job job_1509761346450_0004 running in uber mode : false
17/11/03 21:38:04 INFO mapreduce.Job:  map 0% reduce 0%
17/11/03 21:38:15 INFO mapreduce.Job:  map 4% reduce 0%
17/11/03 21:38:16 INFO mapreduce.Job:  map 11% reduce 0%
17/11/03 21:38:18 INFO mapreduce.Job:  map 16% reduce 0%
17/11/03 21:38:19 INFO mapreduce.Job:  map 21% reduce 0%
17/11/03 21:38:22 INFO mapreduce.Job:  map 28% reduce 0%
17/11/03 21:38:23 INFO mapreduce.Job:  map 29% reduce 0%
17/11/03 21:38:24 INFO mapreduce.Job:  map 30% reduce 0%
17/11/03 21:38:25 INFO mapreduce.Job:  map 33% reduce 0%
17/11/03 21:38:28 INFO mapreduce.Job:  map 37% reduce 0%
17/11/03 21:38:31 INFO mapreduce.Job:  map 40% reduce 0%
17/11/03 21:38:33 INFO mapreduce.Job:  map 48% reduce 0%
17/11/03 21:38:34 INFO mapreduce.Job:  map 52% reduce 0%
17/11/03 21:38:36 INFO mapreduce.Job:  map 56% reduce 0%
17/11/03 21:38:37 INFO mapreduce.Job:  map 58% reduce 0%
17/11/03 21:38:39 INFO mapreduce.Job:  map 62% reduce 0%
17/11/03 21:38:40 INFO mapreduce.Job:  map 66% reduce 0%
17/11/03 21:38:41 INFO mapreduce.Job:  map 67% reduce 0%
17/11/03 21:38:47 INFO mapreduce.Job:  map 69% reduce 0%
17/11/03 21:38:49 INFO mapreduce.Job:  map 71% reduce 0%
17/11/03 21:38:50 INFO mapreduce.Job:  map 75% reduce 0%
17/11/03 21:38:51 INFO mapreduce.Job:  map 78% reduce 0%
17/11/03 21:38:52 INFO mapreduce.Job:  map 80% reduce 0%
17/11/03 21:38:53 INFO mapreduce.Job:  map 83% reduce 0%
17/11/03 21:38:54 INFO mapreduce.Job:  map 86% reduce 0%
17/11/03 21:38:55 INFO mapreduce.Job:  map 89% reduce 0%
17/11/03 21:38:56 INFO mapreduce.Job:  map 91% reduce 0%
17/11/03 21:38:57 INFO mapreduce.Job:  map 93% reduce 0%
17/11/03 21:38:58 INFO mapreduce.Job:  map 96% reduce 0%
17/11/03 21:38:59 INFO mapreduce.Job:  map 97% reduce 0%
17/11/03 21:39:01 INFO mapreduce.Job:  map 100% reduce 0%
17/11/03 21:39:02 INFO mapreduce.Job: Job job_1509761346450_0004 completed successfully
17/11/03 21:39:02 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=1467782
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1025
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=48
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters
		Launched map tasks=12
		Other local map tasks=12
		Total time spent by all maps in occupied slots (ms)=235246
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=235246
		Total vcore-seconds taken by all map tasks=235246
		Total megabyte-seconds taken by all map tasks=240891904
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=1025
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=2773
		CPU time spent (ms)=152350
		Physical memory (bytes) snapshot=4422545408
		Virtual memory (bytes) snapshot=33367277568
		Total committed heap usage (bytes)=4237819904
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=6553600000

real	1m9.165s
user	0m6.264s
sys	0m0.548s

```
* Time Command output
```bash

real	1m9.165s
user	0m6.264s
sys	0m0.548s

```
* The command and output of `hdfs dfs -ls /user/reilly/tgen`
```bash
[reilly@stf-btc-challenge-2 ~]$ hdfs dfs -ls /user/reilly/teragen
Found 13 items
-rw-r--r--   3 reilly reilly          0 2017-11-03 21:39 /user/reilly/teragen/_SUCCESS
-rw-r--r--   3 reilly reilly  546133400 2017-11-03 21:38 /user/reilly/teragen/part-m-00000
-rw-r--r--   3 reilly reilly  546133300 2017-11-03 21:38 /user/reilly/teragen/part-m-00001
-rw-r--r--   3 reilly reilly  546133300 2017-11-03 21:38 /user/reilly/teragen/part-m-00002
-rw-r--r--   3 reilly reilly  546133400 2017-11-03 21:38 /user/reilly/teragen/part-m-00003
-rw-r--r--   3 reilly reilly  546133300 2017-11-03 21:38 /user/reilly/teragen/part-m-00004
-rw-r--r--   3 reilly reilly  546133300 2017-11-03 21:38 /user/reilly/teragen/part-m-00005
-rw-r--r--   3 reilly reilly  546133400 2017-11-03 21:38 /user/reilly/teragen/part-m-00006
-rw-r--r--   3 reilly reilly  546133300 2017-11-03 21:38 /user/reilly/teragen/part-m-00007
-rw-r--r--   3 reilly reilly  546133300 2017-11-03 21:38 /user/reilly/teragen/part-m-00008
-rw-r--r--   3 reilly reilly  546133400 2017-11-03 21:39 /user/reilly/teragen/part-m-00009
-rw-r--r--   3 reilly reilly  546133300 2017-11-03 21:38 /user/reilly/teragen/part-m-00010
-rw-r--r--   3 reilly reilly  546133300 2017-11-03 21:38 /user/reilly/teragen/part-m-00011

```

* The command and output of `hadoop fsck -blocks /user/reilly/tgen`
```bash
[reilly@stf-btc-challenge-2 ~]$ hadoop fsck -blocks /user/reilly/teragen
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://stf-btc-challenge-1.gce.cloudera.com:50070
FSCK started by reilly (auth:SIMPLE) from /172.31.118.147 for path /user/reilly/teragen at Fri Nov 03 21:44:47 PDT 2017
.............Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	1
 Total files:	13
 Total symlinks:		0
 Total blocks (validated):	204 (avg. block size 32125490 B)
 Minimally replicated blocks:	204 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Nov 03 21:44:47 PDT 2017 in 1 milliseconds


The filesystem under path '/user/reilly/teragen' is HEALTHY
[reilly@stf-btc-challenge-2 ~]$`

```

