 * Copy `cloudera-manager.repo` to `challenges/labs/2_cloudera-manager.repo.md`
```bash
[root@stf-btc-challenge-2 ~]# vim /etc/yum.repos.d/cloudera-manager-server.repo

[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RedHat or CentOS 6 x86_64
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/5/
gpgkey =https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 1
```

