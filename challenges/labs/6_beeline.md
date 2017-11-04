
* Create a role `Logger` that can read the `web_logs` database`

NB: Think to add the user `cloudera-scm to the sentry admin groups / restart Sentry to apply the CREATE ROLE and others statements from Sentry.
```bash

[root@stf-btc-challenge-1 ~]# beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.8.5 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-challenge-1.gce.cloudera.com@SCLAIRVILLE.FNG
scan complete in 4ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-challenge-1.gce.cloudera.com@SCLAIRVILLE.FNG
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-challenge-1.gce.cloudera.com@SCLAIRVILLE.FNG: cloudera-scm
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-challenge-1.gce.cloudera.com@SCLAIRVILLE.FNG: ***********
Connected to: Apache Hive (version 1.1.0-cdh5.8.5)
Driver: Hive JDBC (version 1.1.0-cdh5.8.5)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171104002828_7d7710f4-0e83-4f25-8257-72394f79b1c4): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171104002828_7d7710f4-0e83-4f25-8257-72394f79b1c4); Time taken: 0.955 seconds
INFO  : Executing command(queryId=hive_20171104002828_7d7710f4-0e83-4f25-8257-72394f79b1c4): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104002828_7d7710f4-0e83-4f25-8257-72394f79b1c4); Time taken: 0.455 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.918 seconds)
0: jdbc:hive2://localhost:10000/default> create role Logger;
INFO  : Compiling command(queryId=hive_20171104002828_8ec5a276-1965-41ab-bd79-1a76cfddc83b): create role Logger
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171104002828_8ec5a276-1965-41ab-bd79-1a76cfddc83b); Time taken: 0.105 seconds
INFO  : Executing command(queryId=hive_20171104002828_8ec5a276-1965-41ab-bd79-1a76cfddc83b): create role Logger
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104002828_8ec5a276-1965-41ab-bd79-1a76cfddc83b); Time taken: 0.81 seconds
INFO  : OK
No rows affected (0.928 seconds)
0: jdbc:hive2://localhost:10000/default>
```

* The role Logger can read the `web_logs` database
```bash
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE web_logs TO ROLE Logger;
INFO  : Compiling command(queryId=hive_20171104003030_a3417184-5c55-47b7-9b0f-147eef79a788): GRANT SELECT ON DATABASE web_logs TO ROLE Logger
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171104003030_a3417184-5c55-47b7-9b0f-147eef79a788); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20171104003030_a3417184-5c55-47b7-9b0f-147eef79a788): GRANT SELECT ON DATABASE web_logs TO ROLE Logger
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104003030_a3417184-5c55-47b7-9b0f-147eef79a788); Time taken: 0.139 seconds
INFO  : OK
No rows affected (0.22 seconds)
0: jdbc:hive2://localhost:10000/default>
```

* Assign the `sanfrancisco` group to this role
```bash
0: jdbc:hive2://localhost:10000/default> GRANT ROLE Logger TO GROUP sanfrancisco;
INFO  : Compiling command(queryId=hive_20171104003232_f8ac97cc-7a1b-4191-8194-452b1b77cd3f): GRANT ROLE Logger TO GROUP sanfrancisco
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171104003232_f8ac97cc-7a1b-4191-8194-452b1b77cd3f); Time taken: 0.103 seconds
INFO  : Executing command(queryId=hive_20171104003232_f8ac97cc-7a1b-4191-8194-452b1b77cd3f): GRANT ROLE Logger TO GROUP sanfrancisco
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104003232_f8ac97cc-7a1b-4191-8194-452b1b77cd3f); Time taken: 0.088 seconds
INFO  : OK
No rows affected (0.201 seconds)
0: jdbc:hive2://localhost:10000/default>

```

* Create a role for `Customer` that can read the `customers` databases
```bash

0: jdbc:hive2://localhost:10000/default> CREATE ROLE Customer;
INFO  : Compiling command(queryId=hive_20171104003434_e9bacd4c-2c71-4717-a5f5-78f70d79a5c6): CREATE ROLE Customer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171104003434_e9bacd4c-2c71-4717-a5f5-78f70d79a5c6); Time taken: 0.087 seconds
INFO  : Executing command(queryId=hive_20171104003434_e9bacd4c-2c71-4717-a5f5-78f70d79a5c6): CREATE ROLE Customer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104003434_e9bacd4c-2c71-4717-a5f5-78f70d79a5c6); Time taken: 0.046 seconds
INFO  : OK
No rows affected (0.148 seconds)
0: jdbc:hive2://localhost:10000/default>

0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE customers to ROLE Customer;
INFO  : Compiling command(queryId=hive_20171104003535_5bbc9fe1-9638-49ea-9a26-d0b092b62ace): GRANT SELECT ON DATABASE customers to ROLE Customer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171104003535_5bbc9fe1-9638-49ea-9a26-d0b092b62ace); Time taken: 0.061 seconds
INFO  : Executing command(queryId=hive_20171104003535_5bbc9fe1-9638-49ea-9a26-d0b092b62ace): GRANT SELECT ON DATABASE customers to ROLE Customer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104003535_5bbc9fe1-9638-49ea-9a26-d0b092b62ace); Time taken: 0.041 seconds
INFO  : OK
No rows affected (0.117 seconds)

```

  * Assign the `paloalto` group to this role
```bash

0: jdbc:hive2://localhost:10000/default> GRANT ROLE Customer TO GROUP paloalto;
INFO  : Compiling command(queryId=hive_20171104003737_f351d764-2809-48c8-94fc-b09f5698f4e1): GRANT ROLE Customer TO GROUP paloalto
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171104003737_f351d764-2809-48c8-94fc-b09f5698f4e1); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20171104003737_f351d764-2809-48c8-94fc-b09f5698f4e1): GRANT ROLE Customer TO GROUP paloalto
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104003737_f351d764-2809-48c8-94fc-b09f5698f4e1); Time taken: 0.025 seconds
INFO  : OK
No rows affected (0.102 seconds)
```

/// ERROR BETWEEN DATABASES and TABLES in the LAB !!! ///
```bash
GRANT SELECT ON TABLE customers to ROLE Customer;

0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON TABLE customers to ROLE Customer;
INFO  : Compiling command(queryId=hive_20171104004242_38f8fab0-eae8-4dd3-ba1d-e295de471fde): GRANT SELECT ON TABLE customers to ROLE Customer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171104004242_38f8fab0-eae8-4dd3-ba1d-e295de471fde); Time taken: 0.123 seconds
INFO  : Executing command(queryId=hive_20171104004242_38f8fab0-eae8-4dd3-ba1d-e295de471fde): GRANT SELECT ON TABLE customers to ROLE Customer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104004242_38f8fab0-eae8-4dd3-ba1d-e295de471fde); Time taken: 0.068 seconds
INFO  : OK
No rows affected (0.256 seconds)


GRANT SELECT ON TABLE web_logs TO ROLE Logger;
INFO  : Compiling command(queryId=hive_20171104004242_e23fd1f8-eebe-4904-91da-2b2ff6fec3f5): GRANT SELECT ON TABLE web_logs TO ROLE Logger
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171104004242_e23fd1f8-eebe-4904-91da-2b2ff6fec3f5); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20171104004242_e23fd1f8-eebe-4904-91da-2b2ff6fec3f5): GRANT SELECT ON TABLE web_logs TO ROLE Logger
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104004242_e23fd1f8-eebe-4904-91da-2b2ff6fec3f5); Time taken: 0.036 seconds
INFO  : OK
No rows affected (0.114 seconds)

```

```bash
[root@stf-btc-challenge-1 ~]# kinit reilly
Password for reilly@SCLAIRVILLE.FNG:
[root@stf-btc-challenge-1 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: reilly@SCLAIRVILLE.FNG

Valid starting     Expires            Service principal
11/04/17 00:43:14  11/05/17 00:43:14  krbtgt/SCLAIRVILLE.FNG@SCLAIRVILLE.FNG
	renew until 11/10/17 23:43:14
[root@stf-btc-challenge-1 ~]#
[root@stf-btc-challenge-1 ~]#
[root@stf-btc-challenge-1 ~]#
[root@stf-btc-challenge-1 ~]#
[root@stf-btc-challenge-1 ~]# beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.8.5 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-challenge-1.gce.cloudera.com@SCLAIRVILLE.FNG
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-challenge-1.gce.cloudera.com@SCLAIRVILLE.FNG
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-challenge-1.gce.cloudera.com@SCLAIRVILLE.FNG: reilly
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-challenge-1.gce.cloudera.com@SCLAIRVILLE.FNG: *********
Connected to: Apache Hive (version 1.1.0-cdh5.8.5)
Driver: Hive JDBC (version 1.1.0-cdh5.8.5)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171104004343_76eda866-356d-444a-8d19-15cea6533cc6): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171104004343_76eda866-356d-444a-8d19-15cea6533cc6); Time taken: 0.061 seconds
INFO  : Executing command(queryId=hive_20171104004343_76eda866-356d-444a-8d19-15cea6533cc6): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171104004343_76eda866-356d-444a-8d19-15cea6533cc6); Time taken: 0.15 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| web_logs  |
+-----------+--+
1 row selected (0.337 seconds)
0: jdbc:hive2://localhost:10000/default>
```

* Select 10 records from `web_logs`
```bash
0: jdbc:hive2://localhost:10000/default> select * from web_logs limit 10;
INFO  : Compiling command(queryId=hive_20171104004444_67d8983f-4ce8-4d92-892b-7490285b618f): select * from web_logs limit 10
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:web_logs._version_, type:bigint, comment:null), FieldSchema(name:web_logs.app, type:string, comment:null), FieldSchema(name:web_logs.bytes, type:smallint, comment:null), FieldSchema(name:web_logs.city, type:string, comment:null), FieldSchema(name:web_logs.client_ip, type:string, comment:null), FieldSchema(name:web_logs.code, type:tinyint, comment:null), FieldSchema(name:web_logs.country_code, type:string, comment:null), FieldSchema(name:web_logs.country_code3, type:string, comment:null), FieldSchema(name:web_logs.country_name, type:string, comment:null), FieldSchema(name:web_logs.device_family, type:string, comment:null), FieldSchema(name:web_logs.extension, type:string, comment:null), FieldSchema(name:web_logs.latitude, type:float, comment:null), FieldSchema(name:web_logs.longitude, type:float, comment:null), FieldSchema(name:web_logs.method, type:string, comment:null), FieldSchema(name:web_logs.os_family, type:string, comment:null), FieldSchema(name:web_logs.os_major, type:string, comment:null), FieldSchema(name:web_logs.protocol, type:string, comment:null), FieldSchema(name:web_logs.record, type:string, comment:null), FieldSchema(name:web_logs.referer, type:string, comment:null), FieldSchema(name:web_logs.region_code, type:bigint, comment:null), FieldSchema(name:web_logs.request, type:string, comment:null), FieldSchema(name:web_logs.subapp, type:string, comment:null), FieldSchema(name:web_logs.time, type:string, comment:null), FieldSchema(name:web_logs.url, type:string, comment:null), FieldSchema(name:web_logs.user_agent, type:string, comment:null), FieldSchema(name:web_logs.user_agent_family, type:string, comment:null), FieldSchema(name:web_logs.user_agent_major, type:string, comment:null), FieldSchema(name:web_logs.id, type:string, comment:null), FieldSchema(name:web_logs.date, type:string, comment:null)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171104004444_67d8983f-4ce8-4d92-892b-7490285b618f); Time taken: 0.631 seconds
INFO  : Executing command(queryId=hive_20171104004444_67d8983f-4ce8-4d92-892b-7490285b618f): select * from web_logs limit 10
INFO  : Completed executing command(queryId=hive_20171104004444_67d8983f-4ce8-4d92-892b-7490285b618f); Time taken: 0.002 seconds
INFO  : OK
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+------------------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
|  web_logs._version_  | web_logs.app  | web_logs.bytes  | web_logs.city  | web_logs.client_ip  | web_logs.code  | web_logs.country_code  | web_logs.country_code3  | web_logs.country_name  | web_logs.device_family  | web_logs.extension  |  web_logs.latitude  |  web_logs.longitude  | web_logs.method  | web_logs.os_family  | web_logs.os_major  | web_logs.protocol  | web_logs.record  |                                                                                      web_logs.referer                                                                                       | web_logs.region_code  |                                                                                   web_logs.request                                                                                    | web_logs.subapp  |     web_logs.time     |                                                                               web_logs.url                                                                               |                               web_logs.user_agent                               |                 web_logs.user_agent_family                 | web_logs.user_agent_major  |              web_logs.id              | web_logs.date  |
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+------------------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
| 1480895575515725824  | metastore     | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | GET /metastore/table/default/sample_07 HTTP/1.1                                                                                                                                       | table            | 2014-05-04T06:35:49Z  | /metastore/table/default/sample_07                                                                                                                                       | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | 8836e6ce-9a21-449f-a372-9e57641389b3  | 2015-11-18     |
| 1480895575528308736  | metastore     | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | GET /metastore/table/default/sample_07 HTTP/1.1                                                                                                                                       | table            | 2014-05-04T06:35:50Z  | /metastore/table/default/sample_07                                                                                                                                       | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | 6ddf6e38-7b83-423c-8873-39842dca2dbb  | 2015-11-18     |
| 1480895575528308737  | search        | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | GET /search/?collection=10000001 HTTP/1.1                                                                                                                                             |                  | 2014-05-04T06:35:52Z  | /search/?collection=10000001                                                                                                                                             | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | 313bb28e-dd7c-4364-a11e-9ffb0db7b303  | 2015-11-18     |
| 1480895575528308738  | search        | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | GET /search/?collection=10000001 HTTP/1.1                                                                                                                                             |                  | 2014-05-04T06:35:53Z  | /search/?collection=10000001                                                                                                                                             | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | ecb47c61-a9e4-4b59-9234-04bd57695987  | 2015-11-18     |
| 1480895575528308739  |               | 238             | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | HEAD             | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | HEAD / HTTP/1.1                                                                                                                                                                       |                  | 2014-05-04T06:35:54Z  | /                                                                                                                                                                        | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | affdb6b9-3657-4d15-8af8-2ba2f3a69343  | 2015-11-18     |
| 1480895575528308740  | beeswax       | 1041            | Mountain View  | 66.249.76.236       | NULL           | US                     | USA                     | United States          | Spider                  |                     | 37.38600158691406   | -122.08380126953125  | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | NULL                  | GET /beeswax/query_history?q-type=beeswax&amp;q-user=dy8515s&amp;q-auto_query=off HTTP/1.1                                                                                            |                  | 2014-05-04T06:35:54Z  | /beeswax/query_history?q-type=beeswax&amp;q-user=dy8515s&amp;q-auto_query=off                                                                                            | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)        | Googlebot                                                  | 2                          | e3f88d9e-7e5b-4ef7-8941-c0d83720616c  | 2015-11-18     |
| 1480895575528308741  |               | 1041            | Guiyang        | 222.85.131.87       | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 26.58329963684082   | 106.7166976928711    | GET              | Windows 7           |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 18                    | GET / HTTP/1.1                                                                                                                                                                        |                  | 2014-05-04T06:35:55Z  | /                                                                                                                                                                        | Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; Trident/6.0)                | IE                                                         | 10                         | 4dbb1f74-6856-4fe3-8515-c53eab600b60  | 2015-11-18     |
| 1480895575529357312  | desktop       | 0               | Guiyang        | 222.85.131.87       | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 26.58329963684082   | 106.7166976928711    |                  | Other               |                    |                    |                  | -                                                                                                                                                                                           | 18                    | -                                                                                                                                                                                     |                  | 2014-05-04T06:36:16Z  |                                                                                                                                                                          | -                                                                               | Other                                                      |                            | 86cdb56d-99c0-4701-a842-472741bb833a  | 2015-11-18     |
| 1480895575529357313  | search        | 1041            | Shanghai       | 101.226.168.225     | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 31.04560089111328   | 121.39969635009766   | GET              | Windows 7           |                    | HTTP/1.1           |                  | http://demo.gethue.com/search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0  | 23                    | GET /search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0 HTTP/1.1     |                  | 2014-05-04T06:38:31Z  | /search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0     | "Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.1 (KHTML                          |  like Gecko) Chrome/21.0.1180.89 Safari/537.1; 360Spider"  | Chrome                     | 21                                    | 2015-11-18     |
| 1480895575529357314  | search        | 1041            | Mountain View  | 66.249.76.225       | NULL           | US                     | USA                     | United States          | Spider                  |                     | 37.38600158691406   | -122.08380126953125  | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | NULL                  | GET /search/?collection=10000001&amp;query=&amp;fq=%7Cuser_followers_count%3A%5B%22100%22%20TO%20%22199%22%5D%7Cuser_location%3A%22philippines%22&amp;rows=15&amp;start=240 HTTP/1.1  |                  | 2014-05-04T06:38:55Z  | /search/?collection=10000001&amp;query=&amp;fq=%7Cuser_followers_count%3A%5B%22100%22%20TO%20%22199%22%5D%7Cuser_location%3A%22philippines%22&amp;rows=15&amp;start=240  | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)        | Googlebot                                                  | 2                          | 8260ca42-55d6-4cd4-8beb-8767826dc929  | 2015-11-18     |
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+------------------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
10 rows selected (0.998 seconds)
0: jdbc:hive2://localhost:10000/default>
```
