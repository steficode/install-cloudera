* Record the following in `challenges/labs/1_db-server.md`

```bash
[root@stf-btc-challenge-1 ~]# hostname -f
stf-btc-challenge-1.gce.cloudera.com


[root@stf-btc-challenge-1 ~]# mysql -u root -pcloudera123 -e "status";
--------------
mysql  Ver 14.14 Distrib 5.5.58, for Linux (x86_64) using readline 5.1

Connection id:		10
Current database:
Current user:		root@localhost
SSL:			Not in use
Current pager:		stdout
Using outfile:		''
Using delimiter:	;
Server version:		5.5.58 MySQL Community Server (GPL)
Protocol version:	10
Connection:		Localhost via UNIX socket
Server characterset:	latin1
Db     characterset:	latin1
Client characterset:	latin1
Conn.  characterset:	latin1
UNIX socket:		/var/lib/mysql/mysql.sock
Uptime:			46 min 39 sec

Threads: 1  Questions: 30  Slow queries: 0  Opens: 33  Flush tables: 1  Open tables: 26  Queries per second avg: 0.010
--------------

[root@stf-btc-challenge-1 ~]# mysql -u root -pcloudera123 -e "show databases;"
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hue                |
| metastore          |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
| test               |
+--------------------+
```
