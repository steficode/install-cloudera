**Installing MariaBD Server**
> The installation will be done on the node: stf-btc-20171030-1.gce.cloudera.com considered as a master database server

````
[root@stf-btc-20171030-1 network-scripts]# sudo yum install mariadb-server
Failed to set locale, defaulting to C
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirrors.usinternet.com
 * epel: mirror.steadfast.net
 * extras: repo.us.bigstepcloud.com
 * updates: mirror.team-cymru.org
Resolving Dependencies
--> Running transaction check
---> Package mariadb-server.x86_64 1:5.5.56-2.el7 will be installed
--> Processing Dependency: mariadb-libs(x86-64) = 1:5.5.56-2.el7 for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: mariadb(x86-64) = 1:5.5.56-2.el7 for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl-DBI for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl-DBD-MySQL for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(DBI) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.4)(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.1)(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1()(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Running transaction check
---> Package libaio.x86_64 0:0.3.109-13.el7 will be installed
---> Package mariadb.x86_64 1:5.5.56-2.el7 will be installed
---> Package mariadb-libs.x86_64 1:5.5.50-1.el7_2 will be updated
---> Package mariadb-libs.x86_64 1:5.5.56-2.el7 will be an update
---> Package perl-DBD-MySQL.x86_64 0:4.023-5.el7 will be installed
---> Package perl-DBI.x86_64 0:1.627-4.el7 will be installed
--> Processing Dependency: perl(RPC::PlServer) >= 0.2001 for package: perl-DBI-1.627-4.el7.x86_64
--> Processing Dependency: perl(RPC::PlClient) >= 0.2000 for package: perl-DBI-1.627-4.el7.x86_64
--> Running transaction check
---> Package perl-PlRPC.noarch 0:0.2020-14.el7 will be installed
--> Processing Dependency: perl(Net::Daemon) >= 0.13 for package: perl-PlRPC-0.2020-14.el7.noarch
--> Processing Dependency: perl(Net::Daemon::Test) for package: perl-PlRPC-0.2020-14.el7.noarch
--> Processing Dependency: perl(Net::Daemon::Log) for package: perl-PlRPC-0.2020-14.el7.noarch
--> Running transaction check
---> Package perl-Net-Daemon.noarch 0:0.48-5.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

==============================================================================================================================================================
 Package                                    Arch                              Version                                   Repository                       Size
==============================================================================================================================================================
Installing:
 mariadb-server                             x86_64                            1:5.5.56-2.el7                            base                             11 M
Installing for dependencies:
 libaio                                     x86_64                            0.3.109-13.el7                            base                             24 k
 mariadb                                    x86_64                            1:5.5.56-2.el7                            base                            8.7 M
 perl-DBD-MySQL                             x86_64                            4.023-5.el7                               base                            140 k
 perl-DBI                                   x86_64                            1.627-4.el7                               base                            802 k
 perl-Net-Daemon                            noarch                            0.48-5.el7                                base                             51 k
 perl-PlRPC                                 noarch                            0.2020-14.el7                             base                             36 k
Updating for dependencies:
 mariadb-libs                               x86_64                            1:5.5.56-2.el7                            base                            757 k

Transaction Summary
==============================================================================================================================================================
Install  1 Package  (+6 Dependent packages)
Upgrade             ( 1 Dependent package)

Total download size: 22 M
Is this ok [y/d/N]: y
Downloading packages:
Delta RPMs disabled because /usr/bin/applydeltarpm not installed.
(1/8): libaio-0.3.109-13.el7.x86_64.rpm                                                                                                |  24 kB  00:00:00
(2/8): mariadb-libs-5.5.56-2.el7.x86_64.rpm                                                                                            | 757 kB  00:00:00
(3/8): mariadb-5.5.56-2.el7.x86_64.rpm                                                                                                 | 8.7 MB  00:00:02
(4/8): perl-DBD-MySQL-4.023-5.el7.x86_64.rpm                                                                                           | 140 kB  00:00:00
(5/8): perl-DBI-1.627-4.el7.x86_64.rpm                                                                                                 | 802 kB  00:00:00
(6/8): perl-Net-Daemon-0.48-5.el7.noarch.rpm                                                                                           |  51 kB  00:00:00
(7/8): mariadb-server-5.5.56-2.el7.x86_64.rpm                                                                                          |  11 MB  00:00:01
(8/8): perl-PlRPC-0.2020-14.el7.noarch.rpm                                                                                             |  36 kB  00:00:00
--------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                         8.4 MB/s |  22 MB  00:00:02
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Updating   : 1:mariadb-libs-5.5.56-2.el7.x86_64                                                                                                         1/9
  Installing : 1:mariadb-5.5.56-2.el7.x86_64                                                                                                              2/9
  Installing : libaio-0.3.109-13.el7.x86_64                                                                                                               3/9
  Installing : perl-Net-Daemon-0.48-5.el7.noarch                                                                                                          4/9
  Installing : perl-PlRPC-0.2020-14.el7.noarch                                                                                                            5/9
  Installing : perl-DBI-1.627-4.el7.x86_64                                                                                                                6/9
  Installing : perl-DBD-MySQL-4.023-5.el7.x86_64                                                                                                          7/9
  Installing : 1:mariadb-server-5.5.56-2.el7.x86_64                                                                                                       8/9
  Cleanup    : 1:mariadb-libs-5.5.50-1.el7_2.x86_64                                                                                                       9/9
  Verifying  : perl-DBD-MySQL-4.023-5.el7.x86_64                                                                                                          1/9
  Verifying  : perl-Net-Daemon-0.48-5.el7.noarch                                                                                                          2/9
  Verifying  : perl-PlRPC-0.2020-14.el7.noarch                                                                                                            3/9
  Verifying  : 1:mariadb-libs-5.5.56-2.el7.x86_64                                                                                                         4/9
  Verifying  : 1:mariadb-server-5.5.56-2.el7.x86_64                                                                                                       5/9
  Verifying  : libaio-0.3.109-13.el7.x86_64                                                                                                               6/9
  Verifying  : perl-DBI-1.627-4.el7.x86_64                                                                                                                7/9
  Verifying  : 1:mariadb-5.5.56-2.el7.x86_64                                                                                                              8/9
  Verifying  : 1:mariadb-libs-5.5.50-1.el7_2.x86_64                                                                                                       9/9

Installed:
  mariadb-server.x86_64 1:5.5.56-2.el7

Dependency Installed:
  libaio.x86_64 0:0.3.109-13.el7           mariadb.x86_64 1:5.5.56-2.el7          perl-DBD-MySQL.x86_64 0:4.023-5.el7      perl-DBI.x86_64 0:1.627-4.el7
  perl-Net-Daemon.noarch 0:0.48-5.el7      perl-PlRPC.noarch 0:0.2020-14.el7

Dependency Updated:
  mariadb-libs.x86_64 1:5.5.56-2.el7

Complete!
````


**Configuring & Starting MariaDB Server**
````
[root@stf-btc-20171030-1 network-scripts]# sudo service mariadb stop
Redirecting to /bin/systemctl stop  mariadb.service
````

**Edit the configuration file**
```
[root@stf-btc-20171030-1 ~]# sudo vim /etc/my.cnf

		[mysqld]
		transaction-isolation = READ-COMMITTED
		# Disabling symbolic-links is recommended to prevent assorted security risks;
		# to do so, uncomment this line:
		# symbolic-links = 0

		key_buffer = 16M
		key_buffer_size = 32M
		max_allowed_packet = 32M
		thread_stack = 256K
		thread_cache_size = 64
		query_cache_limit = 8M
		query_cache_size = 64M
		query_cache_type = 1

		max_connections = 550
		#expire_logs_days = 10
		#max_binlog_size = 100M

		#log_bin should be on a disk with enough free space. Replace '/var/lib/mysql/mysql_binary_log' with an appropriate path for your system
		#and chown the specified folder to the mysql user.
		log_bin=/var/lib/mysql/mysql_binary_log

		binlog_format = mixed

		read_buffer_size = 2M
		read_rnd_buffer_size = 16M
		sort_buffer_size = 8M
		join_buffer_size = 8M

		# InnoDB settings
		innodb_file_per_table = 1
		innodb_flush_log_at_trx_commit  = 2
		innodb_log_buffer_size = 64M
		innodb_buffer_pool_size = 4G
		innodb_thread_concurrency = 8
		innodb_flush_method = O_DIRECT
		innodb_log_file_size = 512M

		[mysqld_safe]
		log-error=/var/log/mariadb/mariadb.log
		pid-file=/var/run/mariadb/mariadb.pid


````
**Enable MariaDB Server as a service**
```
[root@stf-btc-20171030-1 mysql]#  sudo systemctl enable mariadb
Created symlink from /etc/systemd/system/multi-user.target.wants/mariadb.service to /usr/lib/systemd/system/mariadb.service.
```

**Start MariaDB Server**
```
[root@stf-btc-20171030-1 mysql]# sudo service mariadb start
Redirecting to /bin/systemctl start  mariadb.service
```

**Verify the service status**
```
[root@stf-btc-20171030-1 mysql]# sudo service mariadb status
Redirecting to /bin/systemctl status  mariadb.service
● mariadb.service - MariaDB database server
   Loaded: loaded (/usr/lib/systemd/system/mariadb.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-30 14:34:12 PDT; 37s ago
  Process: 21467 ExecStartPost=/usr/libexec/mariadb-wait-ready $MAINPID (code=exited, status=0/SUCCESS)
  Process: 21391 ExecStartPre=/usr/libexec/mariadb-prepare-db-dir %n (code=exited, status=0/SUCCESS)
 Main PID: 21466 (mysqld_safe)
   CGroup: /system.slice/mariadb.service
           ├─21466 /bin/sh /usr/bin/mysqld_safe --basedir=/usr
           └─21867 /usr/libexec/mysqld --basedir=/usr --datadir=/var/lib/mysql --plugin-dir=/usr/lib64/mysql/plugin --log-error=/var/log/mariadb/mariadb.lo...

Oct 30 14:34:00 stf-btc-20171030-1.gce.cloudera.com systemd[1]: Starting MariaDB database server...
Oct 30 14:34:00 stf-btc-20171030-1.gce.cloudera.com mariadb-prepare-db-dir[21391]: Initializing MariaDB database
Oct 30 14:34:01 stf-btc-20171030-1.gce.cloudera.com mariadb-prepare-db-dir[21391]: 171030 14:34:01 [Note] /usr/libexec/mysqld (mysqld 5.5.56-MariaDB) ...3 ...
Oct 30 14:34:01 stf-btc-20171030-1.gce.cloudera.com mariadb-prepare-db-dir[21391]: 171030 14:34:01 [Note] /usr/libexec/mysqld (mysqld 5.5.56-MariaDB) ...1 ...
Oct 30 14:34:01 stf-btc-20171030-1.gce.cloudera.com mariadb-prepare-db-dir[21391]: PLEASE REMEMBER TO SET A PASSWORD FOR THE MariaDB root USER !
Oct 30 14:34:01 stf-btc-20171030-1.gce.cloudera.com mariadb-prepare-db-dir[21391]: To do so, start the server, then issue the following commands:
Oct 30 14:34:01 stf-btc-20171030-1.gce.cloudera.com mariadb-prepare-db-dir[21391]: '/usr/bin/mysqladmin' -u root password 'new-password'
Oct 30 14:34:02 stf-btc-20171030-1.gce.cloudera.com mysqld_safe[21466]: 171030 14:34:02 mysqld_safe Logging to '/var/log/mariadb/mariadb.log'.
Oct 30 14:34:02 stf-btc-20171030-1.gce.cloudera.com mysqld_safe[21466]: 171030 14:34:02 mysqld_safe Starting mysqld daemon with databases from /var/lib/mysql
Oct 30 14:34:12 stf-btc-20171030-1.gce.cloudera.com systemd[1]: Started MariaDB database server.
Hint: Some lines were ellipsized, use -l to show in full.
```
**Set the MariaDB root password**
```
[root@stf-btc-20171030-1 mysql]# sudo /usr/bin/mysql_secure_installation

NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] Y
New password:
Re-enter new password:
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] Y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] n
 ... skipping.

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] Y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] Y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!
```


**Verification**
``` 
[root@stf-btc-20171030-1 mysql]# mysql -u root
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: NO)
```

## So, in fact, it's right now impossible to connect to MariaDB without password 

> If we pass the argument -p to the connection: 
```
[root@stf-btc-20171030-1 mysql]# mysql -u root -p
Enter password:
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
[root@stf-btc-20171030-1 mysql]# mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 11
Server version: 5.5.56-MariaDB MariaDB Server

Copyright (c) 2000, 2017, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show tables;
ERROR 1046 (3D000): No database selected
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
3 rows in set (0.00 sec)

MariaDB [(none)]> quit;
Bye
```




**Create all the DBs for Cloudera Manager**
```
create database amon DEFAULT CHARACTER SET utf8;
create database rman DEFAULT CHARACTER SET utf8;
create database metastore DEFAULT CHARACTER SET utf8;
create database sentry DEFAULT CHARACTER SET utf8;
create database nav DEFAULT CHARACTER SET utf8;
create database navms DEFAULT CHARACTER SET utf8;


grant all on amon.* TO 'amon'@'stf-btc-20171030-1' IDENTIFIED BY 'amon_password';
grant all on rman.* TO 'rman'@'stf-btc-20171030-1' IDENTIFIED BY 'rman_password';
grant all on rman.* TO 'hive'@'stf-btc-20171030-1' IDENTIFIED BY 'hive_password';
grant all on rman.* TO 'sentry'@'stf-btc-20171030-1' IDENTIFIED BY 'sentry_password';
grant all on rman.* TO 'nav'@'stf-btc-20171030-1' IDENTIFIED BY 'nav_password';
grant all on rman.* TO 'navms'@'stf-btc-20171030-1' IDENTIFIED BY 'navms_password';
```








