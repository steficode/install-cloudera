*  Copy the configuration files in `/var/kerberos/krb5kdc/` to your repo
    * Add the prefix `5_` and the suffix `.md` to the original file name
```bash
[root@stf-btc-challenge-1 krb5kdc]# tar -cvf krb5kdc.tar.gz *
kadm5.acl
kdc.conf
principal
principal.kadm5
principal.kadm5.lock
principal.ok
[root@stf-btc-challenge-1 krb5kdc]# ll
total 204
-rw------- 1 root root  51200 Nov  3 23:52 kadm5.acl
-rw------- 1 root root    499 Nov  3 22:42 kdc.conf
-rw-r--r-- 1 root root 102400 Nov  3 23:52 krb5kdc.tar.gz
-rw------- 1 root root  36864 Nov  3 23:28 principal
-rw------- 1 root root   8192 Nov  3 23:13 principal.kadm5
-rw------- 1 root root      0 Nov  3 22:48 principal.kadm5.lock
-rw------- 1 root root      0 Nov  3 23:28 principal.ok

Transfer via sFTP (fileZilla)
```

