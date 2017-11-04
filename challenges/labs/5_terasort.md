* Run the `terasort` program as user `reilly` with the output target `/user/reilly/tsort`
  	* Use the `tgen` directory as input
```bash
[root@stf-btc-challenge-1 ~]# kinit reilly
Password for reilly@SCLAIRVILLE.FNG:
[root@stf-btc-challenge-1 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: reilly@SCLAIRVILLE.FNG

Valid starting     Expires            Service principal
11/03/17 23:33:50  11/04/17 23:33:50  krbtgt/SCLAIRVILLE.FNG@SCLAIRVILLE.FNG
	renew until 11/10/17 22:33:50
[root@stf-btc-challenge-1 ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/reilly/teragen /user/reilly/tsort
17/11/03 23:34:04 INFO terasort.TeraSort: starting
17/11/03 23:34:06 INFO hdfs.DFSClient: Created token for reilly: HDFS_DELEGATION_TOKEN owner=reilly@SCLAIRVILLE.FNG, renewer=yarn, realUser=, issueDate=1509777246081, maxDate=1510382046081, sequenceNumber=1, masterKeyId=2 on 172.31.118.148:8020
17/11/03 23:34:06 INFO security.TokenCache: Got dt for hdfs://stf-btc-challenge-1.gce.cloudera.com:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.118.148:8020, Ident: (token for reilly: HDFS_DELEGATION_TOKEN owner=reilly@SCLAIRVILLE.FNG, renewer=yarn, realUser=, issueDate=1509777246081, maxDate=1510382046081, sequenceNumber=1, masterKeyId=2)
17/11/03 23:34:06 INFO input.FileInputFormat: Total input paths to process : 12
Spent 378ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 383ms
Sampling 10 splits of 204
Making 4 from 100000 sampled records
Computing parititions took 948ms
Spent 1333ms computing partitions.
17/11/03 23:34:07 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-challenge-1.gce.cloudera.com/172.31.118.148:8032
17/11/03 23:34:07 INFO mapreduce.JobSubmitter: number of splits:204
17/11/03 23:34:08 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509776503043_0001
17/11/03 23:34:08 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.118.148:8020, Ident: (token for reilly: HDFS_DELEGATION_TOKEN owner=reilly@SCLAIRVILLE.FNG, renewer=yarn, realUser=, issueDate=1509777246081, maxDate=1510382046081, sequenceNumber=1, masterKeyId=2)
17/11/03 23:34:09 INFO impl.YarnClientImpl: Submitted application application_1509776503043_0001
17/11/03 23:34:09 INFO mapreduce.Job: The url to track the job: http://stf-btc-challenge-1.gce.cloudera.com:8088/proxy/application_1509776503043_0001/
17/11/03 23:34:09 INFO mapreduce.Job: Running job: job_1509776503043_0001
17/11/03 23:34:20 INFO mapreduce.Job: Job job_1509776503043_0001 running in uber mode : false
17/11/03 23:34:20 INFO mapreduce.Job:  map 0% reduce 0%
17/11/03 23:34:31 INFO mapreduce.Job:  map 1% reduce 0%
17/11/03 23:34:35 INFO mapreduce.Job:  map 2% reduce 0%
17/11/03 23:34:39 INFO mapreduce.Job:  map 3% reduce 0%
17/11/03 23:34:40 INFO mapreduce.Job:  map 4% reduce 0%
17/11/03 23:34:45 INFO mapreduce.Job:  map 5% reduce 0%
17/11/03 23:34:49 INFO mapreduce.Job:  map 6% reduce 0%
17/11/03 23:34:51 INFO mapreduce.Job:  map 7% reduce 0%
17/11/03 23:34:53 INFO mapreduce.Job:  map 8% reduce 0%
17/11/03 23:34:59 INFO mapreduce.Job:  map 9% reduce 0%
17/11/03 23:35:01 INFO mapreduce.Job:  map 10% reduce 0%
17/11/03 23:35:02 INFO mapreduce.Job:  map 11% reduce 0%
17/11/03 23:35:07 INFO mapreduce.Job:  map 12% reduce 0%
17/11/03 23:35:13 INFO mapreduce.Job:  map 13% reduce 0%
17/11/03 23:35:14 INFO mapreduce.Job:  map 14% reduce 0%
17/11/03 23:35:15 INFO mapreduce.Job:  map 15% reduce 0%
17/11/03 23:35:21 INFO mapreduce.Job:  map 16% reduce 0%
17/11/03 23:35:25 INFO mapreduce.Job:  map 17% reduce 0%
17/11/03 23:35:26 INFO mapreduce.Job:  map 18% reduce 0%
17/11/03 23:35:28 INFO mapreduce.Job:  map 19% reduce 0%
17/11/03 23:35:34 INFO mapreduce.Job:  map 20% reduce 0%
17/11/03 23:35:35 INFO mapreduce.Job:  map 21% reduce 0%
17/11/03 23:35:41 INFO mapreduce.Job:  map 22% reduce 0%
17/11/03 23:35:42 INFO mapreduce.Job:  map 23% reduce 0%
17/11/03 23:35:47 INFO mapreduce.Job:  map 24% reduce 0%
17/11/03 23:35:48 INFO mapreduce.Job:  map 25% reduce 0%
17/11/03 23:35:55 INFO mapreduce.Job:  map 26% reduce 0%
17/11/03 23:35:58 INFO mapreduce.Job:  map 27% reduce 0%
17/11/03 23:36:03 INFO mapreduce.Job:  map 29% reduce 0%
17/11/03 23:36:09 INFO mapreduce.Job:  map 30% reduce 0%
17/11/03 23:36:10 INFO mapreduce.Job:  map 31% reduce 0%
17/11/03 23:36:15 INFO mapreduce.Job:  map 32% reduce 0%
17/11/03 23:36:16 INFO mapreduce.Job:  map 33% reduce 0%
17/11/03 23:36:20 INFO mapreduce.Job:  map 34% reduce 0%
17/11/03 23:36:22 INFO mapreduce.Job:  map 35% reduce 0%
17/11/03 23:36:29 INFO mapreduce.Job:  map 36% reduce 0%
17/11/03 23:36:30 INFO mapreduce.Job:  map 37% reduce 0%
17/11/03 23:36:31 INFO mapreduce.Job:  map 38% reduce 0%
17/11/03 23:36:37 INFO mapreduce.Job:  map 39% reduce 0%
17/11/03 23:36:40 INFO mapreduce.Job:  map 40% reduce 0%
17/11/03 23:36:41 INFO mapreduce.Job:  map 41% reduce 0%
17/11/03 23:36:45 INFO mapreduce.Job:  map 42% reduce 0%
17/11/03 23:36:50 INFO mapreduce.Job:  map 43% reduce 0%
17/11/03 23:36:52 INFO mapreduce.Job:  map 44% reduce 0%
17/11/03 23:36:55 INFO mapreduce.Job:  map 45% reduce 0%
17/11/03 23:36:58 INFO mapreduce.Job:  map 46% reduce 0%
17/11/03 23:37:02 INFO mapreduce.Job:  map 47% reduce 0%
17/11/03 23:37:04 INFO mapreduce.Job:  map 48% reduce 0%
17/11/03 23:37:08 INFO mapreduce.Job:  map 49% reduce 0%
17/11/03 23:37:11 INFO mapreduce.Job:  map 50% reduce 0%
17/11/03 23:37:15 INFO mapreduce.Job:  map 51% reduce 0%
17/11/03 23:37:19 INFO mapreduce.Job:  map 52% reduce 0%
17/11/03 23:37:22 INFO mapreduce.Job:  map 53% reduce 0%
17/11/03 23:37:23 INFO mapreduce.Job:  map 54% reduce 0%
17/11/03 23:37:28 INFO mapreduce.Job:  map 55% reduce 0%
17/11/03 23:37:32 INFO mapreduce.Job:  map 56% reduce 0%
17/11/03 23:37:34 INFO mapreduce.Job:  map 57% reduce 0%
17/11/03 23:37:36 INFO mapreduce.Job:  map 58% reduce 0%
17/11/03 23:37:41 INFO mapreduce.Job:  map 59% reduce 0%
17/11/03 23:37:42 INFO mapreduce.Job:  map 60% reduce 0%
17/11/03 23:37:47 INFO mapreduce.Job:  map 61% reduce 0%
17/11/03 23:37:49 INFO mapreduce.Job:  map 62% reduce 0%
17/11/03 23:37:52 INFO mapreduce.Job:  map 63% reduce 0%
17/11/03 23:37:56 INFO mapreduce.Job:  map 64% reduce 0%
17/11/03 23:38:00 INFO mapreduce.Job:  map 65% reduce 0%
17/11/03 23:38:02 INFO mapreduce.Job:  map 66% reduce 0%
17/11/03 23:38:03 INFO mapreduce.Job:  map 67% reduce 0%
17/11/03 23:38:08 INFO mapreduce.Job:  map 68% reduce 0%
17/11/03 23:38:11 INFO mapreduce.Job:  map 69% reduce 0%
17/11/03 23:38:14 INFO mapreduce.Job:  map 70% reduce 0%
17/11/03 23:38:17 INFO mapreduce.Job:  map 71% reduce 0%
17/11/03 23:38:22 INFO mapreduce.Job:  map 72% reduce 0%
17/11/03 23:38:23 INFO mapreduce.Job:  map 73% reduce 0%
17/11/03 23:38:25 INFO mapreduce.Job:  map 74% reduce 0%
17/11/03 23:38:29 INFO mapreduce.Job:  map 75% reduce 0%
17/11/03 23:38:34 INFO mapreduce.Job:  map 76% reduce 0%
17/11/03 23:38:36 INFO mapreduce.Job:  map 77% reduce 0%
17/11/03 23:38:43 INFO mapreduce.Job:  map 79% reduce 0%
17/11/03 23:38:45 INFO mapreduce.Job:  map 80% reduce 0%
17/11/03 23:38:49 INFO mapreduce.Job:  map 81% reduce 0%
17/11/03 23:38:54 INFO mapreduce.Job:  map 82% reduce 0%
17/11/03 23:38:55 INFO mapreduce.Job:  map 83% reduce 0%
17/11/03 23:38:57 INFO mapreduce.Job:  map 84% reduce 0%
17/11/03 23:39:05 INFO mapreduce.Job:  map 85% reduce 0%
17/11/03 23:39:06 INFO mapreduce.Job:  map 85% reduce 3%
17/11/03 23:39:07 INFO mapreduce.Job:  map 85% reduce 6%
17/11/03 23:39:08 INFO mapreduce.Job:  map 85% reduce 10%
17/11/03 23:39:09 INFO mapreduce.Job:  map 85% reduce 12%
17/11/03 23:39:10 INFO mapreduce.Job:  map 85% reduce 13%
17/11/03 23:39:11 INFO mapreduce.Job:  map 85% reduce 14%
17/11/03 23:39:13 INFO mapreduce.Job:  map 85% reduce 15%
17/11/03 23:39:14 INFO mapreduce.Job:  map 85% reduce 16%
17/11/03 23:39:15 INFO mapreduce.Job:  map 86% reduce 18%
17/11/03 23:39:16 INFO mapreduce.Job:  map 86% reduce 19%
17/11/03 23:39:17 INFO mapreduce.Job:  map 86% reduce 20%
17/11/03 23:39:18 INFO mapreduce.Job:  map 86% reduce 21%
17/11/03 23:39:21 INFO mapreduce.Job:  map 86% reduce 22%
17/11/03 23:39:23 INFO mapreduce.Job:  map 87% reduce 22%
17/11/03 23:39:29 INFO mapreduce.Job:  map 88% reduce 22%
17/11/03 23:39:37 INFO mapreduce.Job:  map 89% reduce 22%
17/11/03 23:39:45 INFO mapreduce.Job:  map 90% reduce 22%
17/11/03 23:39:48 INFO mapreduce.Job:  map 90% reduce 23%
17/11/03 23:39:51 INFO mapreduce.Job:  map 91% reduce 23%
17/11/03 23:39:57 INFO mapreduce.Job:  map 92% reduce 23%
17/11/03 23:40:03 INFO mapreduce.Job:  map 93% reduce 23%
17/11/03 23:40:10 INFO mapreduce.Job:  map 94% reduce 23%
17/11/03 23:40:15 INFO mapreduce.Job:  map 95% reduce 24%
17/11/03 23:40:21 INFO mapreduce.Job:  map 96% reduce 24%
17/11/03 23:40:26 INFO mapreduce.Job:  map 97% reduce 24%
17/11/03 23:40:31 INFO mapreduce.Job:  map 98% reduce 24%
17/11/03 23:40:36 INFO mapreduce.Job:  map 99% reduce 24%
17/11/03 23:40:37 INFO mapreduce.Job:  map 99% reduce 25%
17/11/03 23:40:41 INFO mapreduce.Job:  map 100% reduce 25%
17/11/03 23:40:48 INFO mapreduce.Job:  map 100% reduce 30%
17/11/03 23:40:49 INFO mapreduce.Job:  map 100% reduce 35%
17/11/03 23:40:50 INFO mapreduce.Job:  map 100% reduce 43%
17/11/03 23:40:51 INFO mapreduce.Job:  map 100% reduce 47%
17/11/03 23:40:52 INFO mapreduce.Job:  map 100% reduce 53%
17/11/03 23:40:53 INFO mapreduce.Job:  map 100% reduce 54%
17/11/03 23:40:54 INFO mapreduce.Job:  map 100% reduce 55%
17/11/03 23:40:55 INFO mapreduce.Job:  map 100% reduce 56%
17/11/03 23:40:56 INFO mapreduce.Job:  map 100% reduce 57%
17/11/03 23:40:57 INFO mapreduce.Job:  map 100% reduce 58%
17/11/03 23:40:58 INFO mapreduce.Job:  map 100% reduce 59%
17/11/03 23:40:59 INFO mapreduce.Job:  map 100% reduce 60%
17/11/03 23:41:00 INFO mapreduce.Job:  map 100% reduce 61%
17/11/03 23:41:01 INFO mapreduce.Job:  map 100% reduce 63%
17/11/03 23:41:02 INFO mapreduce.Job:  map 100% reduce 64%
17/11/03 23:41:03 INFO mapreduce.Job:  map 100% reduce 65%
17/11/03 23:41:04 INFO mapreduce.Job:  map 100% reduce 66%
17/11/03 23:41:05 INFO mapreduce.Job:  map 100% reduce 67%
17/11/03 23:41:06 INFO mapreduce.Job:  map 100% reduce 68%
17/11/03 23:41:07 INFO mapreduce.Job:  map 100% reduce 71%
17/11/03 23:41:08 INFO mapreduce.Job:  map 100% reduce 72%
17/11/03 23:41:09 INFO mapreduce.Job:  map 100% reduce 73%
17/11/03 23:41:10 INFO mapreduce.Job:  map 100% reduce 74%
17/11/03 23:41:11 INFO mapreduce.Job:  map 100% reduce 75%
17/11/03 23:41:12 INFO mapreduce.Job:  map 100% reduce 76%
17/11/03 23:41:13 INFO mapreduce.Job:  map 100% reduce 82%
17/11/03 23:41:14 INFO mapreduce.Job:  map 100% reduce 83%
17/11/03 23:41:16 INFO mapreduce.Job:  map 100% reduce 88%
17/11/03 23:41:19 INFO mapreduce.Job:  map 100% reduce 90%
17/11/03 23:41:22 INFO mapreduce.Job:  map 100% reduce 91%
17/11/03 23:41:25 INFO mapreduce.Job:  map 100% reduce 93%
17/11/03 23:41:28 INFO mapreduce.Job:  map 100% reduce 94%
17/11/03 23:41:31 INFO mapreduce.Job:  map 100% reduce 95%
17/11/03 23:41:34 INFO mapreduce.Job:  map 100% reduce 97%
17/11/03 23:41:37 INFO mapreduce.Job:  map 100% reduce 98%
17/11/03 23:41:40 INFO mapreduce.Job:  map 100% reduce 99%
17/11/03 23:41:42 INFO mapreduce.Job:  map 100% reduce 100%
17/11/03 23:41:43 INFO mapreduce.Job: Job job_1509776503043_0001 completed successfully
17/11/03 23:41:43 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=2938078489
		FILE: Number of bytes written=5831328177
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=6553629784
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=624
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters
		Launched map tasks=204
		Launched reduce tasks=4
		Data-local map tasks=202
		Rack-local map tasks=2
		Total time spent by all maps in occupied slots (ms)=1380232
		Total time spent by all reduces in occupied slots (ms)=485349
		Total time spent by all map tasks (ms)=1380232
		Total time spent by all reduce tasks (ms)=485349
		Total vcore-seconds taken by all map tasks=1380232
		Total vcore-seconds taken by all reduce tasks=485349
		Total megabyte-seconds taken by all map tasks=1413357568
		Total megabyte-seconds taken by all reduce tasks=496997376
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Map output bytes=6684672000
		Map output materialized bytes=2867347318
		Input split bytes=29784
		Combine input records=0
		Combine output records=0
		Reduce input groups=65536000
		Reduce shuffle bytes=2867347318
		Reduce input records=65536000
		Reduce output records=65536000
		Spilled Records=131072000
		Shuffled Maps =816
		Failed Shuffles=0
		Merged Map outputs=816
		GC time elapsed (ms)=32584
		CPU time spent (ms)=1045810
		Physical memory (bytes) snapshot=96077217792
		Virtual memory (bytes) snapshot=574676418560
		Total committed heap usage (bytes)=97777090560
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=6553600000
	File Output Format Counters
		Bytes Written=6553600000
17/11/03 23:41:43 INFO terasort.TeraSort: done

real	7m39.988s
user	0m9.218s
sys	0m0.612s

```

