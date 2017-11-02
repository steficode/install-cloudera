##A Quick Sentry Tutorial
**Verify user privileges**
```
My Cluster Boomerang has been Kerberized

!connect jdbc:hive2://localhost:10000/default;principal=hive/`hostname -f`@STEFUN.COM

0: jdbc:hive2://localhost:10000/default (closed)> !connect jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
1: jdbc:hive2://localhost:10000/default> show databases;
+----------------+--+
| database_name  |
+----------------+--+
| default        |
+----------------+--+
1 row selected (1.218 seconds)
INFO  : Compiling command(queryId=hive_20171102141515_8fe73dcb-7e0f-43c2-8610-339f4e424abf): show databases
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:database_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171102141515_8fe73dcb-7e0f-43c2-8610-339f4e424abf); Time taken: 0.66 seconds
INFO  : Executing command(queryId=hive_20171102141515_8fe73dcb-7e0f-43c2-8610-339f4e424abf): show databases
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102141515_8fe73dcb-7e0f-43c2-8610-339f4e424abf); Time taken: 0.072 seconds
INFO  : OK
1: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171102141515_b0c5680b-91dd-4994-97a1-9e32b3a49452): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171102141515_b0c5680b-91dd-4994-97a1-9e32b3a49452); Time taken: 0.007 seconds
INFO  : Executing command(queryId=hive_20171102141515_b0c5680b-91dd-4994-97a1-9e32b3a49452): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102141515_b0c5680b-91dd-4994-97a1-9e32b3a49452); Time taken: 0.033 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.059 seconds)
```

**Add Sentry Service to Boomerang**
```
////
Hadoop Groups
Go to the Hive service.
Click the Configuration tab.
Select Scope > Hive (Service-Wide).
Select Category > Policy File Based Sentry.
Locate the Sentry User to Group Mapping Class property or search for it by typing its name in the Search box.
Set the Sentry User to Group Mapping Class property to org.apache.sentry.provider.file.HadoopGroupResourceAuthorizationProvider.
Click Save Changes.
Restart the Hive service.
////

Add the following string to the Java configuration options for HiveServer2 during startup.
-Dsentry.allow.uri.db.policyfile=true
```

**Configure Sentry to recognize this account as an administrator**

```
Creating a Kerberos Principal for Sentry:

[root@stf-btc-20171030-5 ~]# kadmin.local
Authenticating as principal sclairville/admin@STEFUN.COM with password.
kadmin.local:  addprinc sentry@STEFUN.COM
WARNING: no policy specified for sentry@STEFUN.COM; defaulting to no policy
Enter password for principal "sentry@STEFUN.COM":
Re-enter password for principal "sentry@STEFUN.COM":
Principal "sentry@STEFUN.COM" created.
kadmin.local:  exit
```

**Create a Sentry role with full authorization**
```
[root@stf-btc-20171030-1 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: sclairville@STEFUN.COM

Valid starting     Expires            Service principal
11/02/17 15:38:24  11/03/17 15:38:24  krbtgt/STEFUN.COM@STEFUN.COM
	renew until 11/09/17 14:38:24
[root@stf-btc-20171030-1 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> create role sentry_admin;
INFO  : Compiling command(queryId=hive_20171102154747_8259b465-51b0-430f-9221-49676aed406f): create role sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102154747_8259b465-51b0-430f-9221-49676aed406f); Time taken: 0.094 seconds
INFO  : Executing command(queryId=hive_20171102154747_8259b465-51b0-430f-9221-49676aed406f): create role sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102154747_8259b465-51b0-430f-9221-49676aed406f); Time taken: 0.034 seconds
INFO  : OK
No rows affected (0.221 seconds)
0: jdbc:hive2://localhost:10000/default>

0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171102154848_1c2883d6-b642-4494-ac37-5940fef6b849): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171102154848_1c2883d6-b642-4494-ac37-5940fef6b849); Time taken: 0.281 seconds
INFO  : Executing command(queryId=hive_20171102154848_1c2883d6-b642-4494-ac37-5940fef6b849): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102154848_1c2883d6-b642-4494-ac37-5940fef6b849); Time taken: 0.27 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.645 seconds)
0: jdbc:hive2://localhost:10000/default> show databases;
INFO  : Compiling command(queryId=hive_20171102154848_85e678d9-3227-4271-96da-929461dd203c): show databases
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:database_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171102154848_85e678d9-3227-4271-96da-929461dd203c); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20171102154848_85e678d9-3227-4271-96da-929461dd203c): show databases
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102154848_85e678d9-3227-4271-96da-929461dd203c); Time taken: 0.134 seconds
INFO  : OK
+----------------+--+
| database_name  |
+----------------+--+
| default        |
+----------------+--+
1 row selected (0.26 seconds)



0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171102155050_e7048e66-51a3-44b0-8f22-07b73cb7d6eb): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102155050_e7048e66-51a3-44b0-8f22-07b73cb7d6eb); Time taken: 0.086 seconds
INFO  : Executing command(queryId=hive_20171102155050_e7048e66-51a3-44b0-8f22-07b73cb7d6eb): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102155050_e7048e66-51a3-44b0-8f22-07b73cb7d6eb); Time taken: 0.091 seconds
INFO  : OK
No rows affected (0.192 seconds)
0: jdbc:hive2://localhost:10000/default>



0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP sclairville;
INFO  : Compiling command(queryId=hive_20171102155151_110c6689-a2ab-4656-b0e5-1e97d99be9b9): GRANT ROLE sentry_admin TO GROUP sclairville
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102155151_110c6689-a2ab-4656-b0e5-1e97d99be9b9); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20171102155151_110c6689-a2ab-4656-b0e5-1e97d99be9b9): GRANT ROLE sentry_admin TO GROUP sclairville
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102155151_110c6689-a2ab-4656-b0e5-1e97d99be9b9); Time taken: 0.091 seconds
INFO  : OK
No rows affected (0.173 seconds)


0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171102155252_32bbf243-d526-45b9-815b-9e1755ff9278): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171102155252_32bbf243-d526-45b9-815b-9e1755ff9278); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20171102155252_32bbf243-d526-45b9-815b-9e1755ff9278): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102155252_32bbf243-d526-45b9-815b-9e1755ff9278); Time taken: 0.154 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.232 seconds)
0: jdbc:hive2://localhost:10000/default>

```

**Create additional test users**

```

for host in stf-btc-20171030-1 stf-btc-20171030-2 stf-btc-20171030-3 stf-btc-20171030-4 stf-btc-20171030-5;
do ssh -o StrictHostKeyChecking=no root@$host "sudo groupadd selector";
done


for host in stf-btc-20171030-1 stf-btc-20171030-2 stf-btc-20171030-3 stf-btc-20171030-4 stf-btc-20171030-5;
do ssh -o StrictHostKeyChecking=no root@$host "sudo groupadd inserters";
done

for host in stf-btc-20171030-1 stf-btc-20171030-2 stf-btc-20171030-3 stf-btc-20171030-4 stf-btc-20171030-5;
do ssh -o StrictHostKeyChecking=no root@$host "sudo useradd -u 1100 -g selector george";
done


for host in stf-btc-20171030-1 stf-btc-20171030-2 stf-btc-20171030-3 stf-btc-20171030-4 stf-btc-20171030-5;
do ssh -o StrictHostKeyChecking=no root@$host "sudo useradd -u 1200 -g inserters ferdinand";
done

[root@stf-btc-20171030-5 ~]# kadmin.local: add_principal george
-bash: kadmin.local:: command not found
[root@stf-btc-20171030-5 ~]# kadmin.local
Authenticating as principal sclairville/admin@STEFUN.COM with password.
kadmin.local:  add_principal george
WARNING: no policy specified for george@STEFUN.COM; defaulting to no policy
Enter password for principal "george@STEFUN.COM":
Re-enter password for principal "george@STEFUN.COM":
add_principal: Password mismatch while reading password for "george@STEFUN.COM".
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@STEFUN.COM; defaulting to no policy
Enter password for principal "ferdinand@STEFUN.COM":
Re-enter password for principal "ferdinand@STEFUN.COM":
add_principal: Password mismatch while reading password for "ferdinand@STEFUN.COM".
kadmin.local:  exit;
kadmin.local: Unknown request "exit;".  Type "?" for a request list.
kadmin.local:  exit

```

**Create test roles**
```
[root@stf-btc-20171030-1 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171102155959_1794ab96-4959-49b2-ad8d-dc82dd680599): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171102155959_1794ab96-4959-49b2-ad8d-dc82dd680599); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20171102155959_1794ab96-4959-49b2-ad8d-dc82dd680599): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102155959_1794ab96-4959-49b2-ad8d-dc82dd680599); Time taken: 0.139 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.309 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20171102160000_e0e1f99b-86ba-4932-86d9-f9d9428e7204): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102160000_e0e1f99b-86ba-4932-86d9-f9d9428e7204); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20171102160000_e0e1f99b-86ba-4932-86d9-f9d9428e7204): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102160000_e0e1f99b-86ba-4932-86d9-f9d9428e7204); Time taken: 0.04 seconds
INFO  : OK
No rows affected (0.121 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20171102160000_ff1559ff-34ee-415b-be2c-1a327f9401b4): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102160000_ff1559ff-34ee-415b-be2c-1a327f9401b4); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20171102160000_ff1559ff-34ee-415b-be2c-1a327f9401b4): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102160000_ff1559ff-34ee-415b-be2c-1a327f9401b4); Time taken: 0.024 seconds
INFO  : OK
No rows affected (0.106 seconds)
0: jdbc:hive2://localhost:10000/default>

0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20171102160000_d62073d8-3a33-4c6d-9d87-23220fd2f96c): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102160000_d62073d8-3a33-4c6d-9d87-23220fd2f96c); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20171102160000_d62073d8-3a33-4c6d-9d87-23220fd2f96c): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102160000_d62073d8-3a33-4c6d-9d87-23220fd2f96c); Time taken: 0.03 seconds
INFO  : OK
No rows affected (0.111 seconds)


0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20171102160101_2d8e57f8-ca44-45c3-8f49-378e7816f5fc): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102160101_2d8e57f8-ca44-45c3-8f49-378e7816f5fc); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20171102160101_2d8e57f8-ca44-45c3-8f49-378e7816f5fc): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102160101_2d8e57f8-ca44-45c3-8f49-378e7816f5fc); Time taken: 0.027 seconds
INFO  : OK
No rows affected (0.097 seconds)

```

**Grant read privilege for default.sample07 only to 'writes'**
```

0: jdbc:hive2://localhost:10000/default> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20171102160202_b86ef6dc-e91d-46ab-91a7-314c336828f9): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102160202_b86ef6dc-e91d-46ab-91a7-314c336828f9); Time taken: 0.069 seconds
INFO  : Executing command(queryId=hive_20171102160202_b86ef6dc-e91d-46ab-91a7-314c336828f9): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102160202_b86ef6dc-e91d-46ab-91a7-314c336828f9); Time taken: 0.09 seconds
INFO  : OK
No rows affected (0.173 seconds)

0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20171102160202_2a72837a-cc4f-4976-94c6-3d3f3a8dc394): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102160202_2a72837a-cc4f-4976-94c6-3d3f3a8dc394); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20171102160202_2a72837a-cc4f-4976-94c6-3d3f3a8dc394): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102160202_2a72837a-cc4f-4976-94c6-3d3f3a8dc394); Time taken: 0.032 seconds
INFO  : OK
No rows affected (0.116 seconds)

0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20171102160202_eaffcf29-7851-414a-adad-e734aebb39c6): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171102160202_eaffcf29-7851-414a-adad-e734aebb39c6); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20171102160202_eaffcf29-7851-414a-adad-e734aebb39c6): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102160202_eaffcf29-7851-414a-adad-e734aebb39c6); Time taken: 0.028 seconds
INFO  : OK
No rows affected (0.098 seconds)

```

**kinit as specific user, then login to beeline**
### George
```
[root@stf-btc-20171030-1 ~]# kinit george
Password for george@STEFUN.COM:
[root@stf-btc-20171030-1 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: george@STEFUN.COM

Valid starting     Expires            Service principal
11/02/17 16:06:53  11/03/17 16:06:53  krbtgt/STEFUN.COM@STEFUN.COM
	renew until 11/09/17 15:06:53
[root@stf-btc-20171030-1 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171102160707_58847eaf-65f7-4de9-9751-8487904ebdc0): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171102160707_58847eaf-65f7-4de9-9751-8487904ebdc0); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20171102160707_58847eaf-65f7-4de9-9751-8487904ebdc0): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102160707_58847eaf-65f7-4de9-9751-8487904ebdc0); Time taken: 0.138 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.316 seconds)

It's OK George can see all the tables into Hive

```
### Ferdinand
```
[root@stf-btc-20171030-1 ~]# kdestroy -A
[root@stf-btc-20171030-1 ~]# klist
klist: No credentials cache found (filename: /tmp/krb5cc_0)

[root@stf-btc-20171030-1 ~]# kinit ferdinand
Password for ferdinand@STEFUN.COM:
[root@stf-btc-20171030-1 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: ferdinand@STEFUN.COM

Valid starting     Expires            Service principal
11/02/17 16:11:29  11/03/17 16:11:29  krbtgt/STEFUN.COM@STEFUN.COM
	renew until 11/09/17 15:11:29

[root@stf-btc-20171030-1 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/stf-btc-20171030-1.gce.cloudera.com@STEFUN.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171102161212_8020c360-ec2b-442e-bb59-1e459ef9fd13): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171102161212_8020c360-ec2b-442e-bb59-1e459ef9fd13); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20171102161212_8020c360-ec2b-442e-bb59-1e459ef9fd13): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171102161212_8020c360-ec2b-442e-bb59-1e459ef9fd13); Time taken: 0.143 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.324 seconds)

It's OK: Ferdinand has a limited access and can see only one table "default.sample_07"

```
:-)

