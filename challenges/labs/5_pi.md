* Run the Hadoop `pi` program as user `frankola`
  * Use the task parameters `50` and `100` 
  * Copy the command and full output to `challenges/labs/5_pi.md`
```bash
[root@stf-btc-challenge-1 ~]# kinit frankola
Password for frankola@SCLAIRVILLE.FNG:
[root@stf-btc-challenge-1 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: frankola@SCLAIRVILLE.FNG

Valid starting     Expires            Service principal
11/03/17 23:44:17  11/04/17 23:44:17  krbtgt/SCLAIRVILLE.FNG@SCLAIRVILLE.FNG
	renew until 11/10/17 22:44:17
[root@stf-btc-challenge-1 ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 50 100
Number of Maps  = 50
Samples per Map = 100
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Wrote input for Map #10
Wrote input for Map #11
Wrote input for Map #12
Wrote input for Map #13
Wrote input for Map #14
Wrote input for Map #15
Wrote input for Map #16
Wrote input for Map #17
Wrote input for Map #18
Wrote input for Map #19
Wrote input for Map #20
Wrote input for Map #21
Wrote input for Map #22
Wrote input for Map #23
Wrote input for Map #24
Wrote input for Map #25
Wrote input for Map #26
Wrote input for Map #27
Wrote input for Map #28
Wrote input for Map #29
Wrote input for Map #30
Wrote input for Map #31
Wrote input for Map #32
Wrote input for Map #33
Wrote input for Map #34
Wrote input for Map #35
Wrote input for Map #36
Wrote input for Map #37
Wrote input for Map #38
Wrote input for Map #39
Wrote input for Map #40
Wrote input for Map #41
Wrote input for Map #42
Wrote input for Map #43
Wrote input for Map #44
Wrote input for Map #45
Wrote input for Map #46
Wrote input for Map #47
Wrote input for Map #48
Wrote input for Map #49
Starting Job
17/11/03 23:45:21 INFO client.RMProxy: Connecting to ResourceManager at stf-btc-challenge-1.gce.cloudera.com/172.31.118.148:8032
17/11/03 23:45:21 INFO hdfs.DFSClient: Created token for frankola: HDFS_DELEGATION_TOKEN owner=frankola@SCLAIRVILLE.FNG, renewer=yarn, realUser=, issueDate=1509777921566, maxDate=1510382721566, sequenceNumber=2, masterKeyId=2 on 172.31.118.148:8020
17/11/03 23:45:21 INFO security.TokenCache: Got dt for hdfs://stf-btc-challenge-1.gce.cloudera.com:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.118.148:8020, Ident: (token for frankola: HDFS_DELEGATION_TOKEN owner=frankola@SCLAIRVILLE.FNG, renewer=yarn, realUser=, issueDate=1509777921566, maxDate=1510382721566, sequenceNumber=2, masterKeyId=2)
17/11/03 23:45:21 INFO input.FileInputFormat: Total input paths to process : 50
17/11/03 23:45:21 INFO mapreduce.JobSubmitter: number of splits:50
17/11/03 23:45:21 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509776503043_0002
17/11/03 23:45:21 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.118.148:8020, Ident: (token for frankola: HDFS_DELEGATION_TOKEN owner=frankola@SCLAIRVILLE.FNG, renewer=yarn, realUser=, issueDate=1509777921566, maxDate=1510382721566, sequenceNumber=2, masterKeyId=2)
17/11/03 23:45:22 INFO impl.YarnClientImpl: Submitted application application_1509776503043_0002
17/11/03 23:45:22 INFO mapreduce.Job: The url to track the job: http://stf-btc-challenge-1.gce.cloudera.com:8088/proxy/application_1509776503043_0002/
17/11/03 23:45:22 INFO mapreduce.Job: Running job: job_1509776503043_0002
17/11/03 23:45:33 INFO mapreduce.Job: Job job_1509776503043_0002 running in uber mode : false
17/11/03 23:45:33 INFO mapreduce.Job:  map 0% reduce 0%
17/11/03 23:45:42 INFO mapreduce.Job:  map 2% reduce 0%
17/11/03 23:45:46 INFO mapreduce.Job:  map 8% reduce 0%
17/11/03 23:45:47 INFO mapreduce.Job:  map 12% reduce 0%
17/11/03 23:45:50 INFO mapreduce.Job:  map 14% reduce 0%
17/11/03 23:45:53 INFO mapreduce.Job:  map 18% reduce 0%
17/11/03 23:45:54 INFO mapreduce.Job:  map 24% reduce 0%
17/11/03 23:45:59 INFO mapreduce.Job:  map 26% reduce 0%
17/11/03 23:46:00 INFO mapreduce.Job:  map 30% reduce 0%
17/11/03 23:46:01 INFO mapreduce.Job:  map 34% reduce 0%
17/11/03 23:46:03 INFO mapreduce.Job:  map 36% reduce 0%
17/11/03 23:46:07 INFO mapreduce.Job:  map 42% reduce 0%
17/11/03 23:46:08 INFO mapreduce.Job:  map 46% reduce 0%
17/11/03 23:46:11 INFO mapreduce.Job:  map 48% reduce 0%
17/11/03 23:46:14 INFO mapreduce.Job:  map 52% reduce 0%
17/11/03 23:46:15 INFO mapreduce.Job:  map 58% reduce 0%
17/11/03 23:46:19 INFO mapreduce.Job:  map 60% reduce 0%
17/11/03 23:46:21 INFO mapreduce.Job:  map 64% reduce 0%
17/11/03 23:46:22 INFO mapreduce.Job:  map 68% reduce 0%
17/11/03 23:46:23 INFO mapreduce.Job:  map 70% reduce 0%
17/11/03 23:46:27 INFO mapreduce.Job:  map 72% reduce 0%
17/11/03 23:46:28 INFO mapreduce.Job:  map 76% reduce 0%
17/11/03 23:46:29 INFO mapreduce.Job:  map 80% reduce 0%
17/11/03 23:46:31 INFO mapreduce.Job:  map 82% reduce 0%
17/11/03 23:46:35 INFO mapreduce.Job:  map 86% reduce 0%
17/11/03 23:46:36 INFO mapreduce.Job:  map 92% reduce 0%
17/11/03 23:46:42 INFO mapreduce.Job:  map 94% reduce 0%
17/11/03 23:46:43 INFO mapreduce.Job:  map 100% reduce 0%
17/11/03 23:46:44 INFO mapreduce.Job:  map 100% reduce 100%
17/11/03 23:46:44 INFO mapreduce.Job: Job job_1509776503043_0002 completed successfully
17/11/03 23:46:44 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=264
		FILE: Number of bytes written=6314933
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=14740
		HDFS: Number of bytes written=215
		HDFS: Number of read operations=203
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Job Counters
		Launched map tasks=50
		Launched reduce tasks=1
		Data-local map tasks=50
		Total time spent by all maps in occupied slots (ms)=286115
		Total time spent by all reduces in occupied slots (ms)=7827
		Total time spent by all map tasks (ms)=286115
		Total time spent by all reduce tasks (ms)=7827
		Total vcore-seconds taken by all map tasks=286115
		Total vcore-seconds taken by all reduce tasks=7827
		Total megabyte-seconds taken by all map tasks=292981760
		Total megabyte-seconds taken by all reduce tasks=8014848
	Map-Reduce Framework
		Map input records=50
		Map output records=100
		Map output bytes=900
		Map output materialized bytes=1700
		Input split bytes=8840
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=1700
		Reduce input records=100
		Reduce output records=0
		Spilled Records=200
		Shuffled Maps =50
		Failed Shuffles=0
		Merged Map outputs=50
		GC time elapsed (ms)=6875
		CPU time spent (ms)=32230
		Physical memory (bytes) snapshot=21897158656
		Virtual memory (bytes) snapshot=140703387648
		Total committed heap usage (bytes)=22515023872
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=5900
	File Output Format Counters
		Bytes Written=97
Job Finished in 83.238 seconds
Estimated value of Pi is 3.14160000000000000000

real	1m27.017s
user	0m7.954s
sys	0m0.444s

```

