>> Define the variables for the CM_Server API
```bash
CMS_URL=http://stf-btc-20171030-1.gce.cloudera.com
CMS_PORT=7180
CMS_PATH_SERVICES=api/v1/clusters/Boomerang/services
CM_USER=sclairville
CM_PASS=cloudera
```

## Report the latest available version of the API
```bash
[root@stf-btc-20171030-1 ~]# curl -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/api/version"
v14
```

## Report the CM version
```bash
[root@stf-btc-20171030-1 ~]# curl -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/api/v14/cm/version"
{
  "version" : "5.9.3",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170627-1506",
  "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
  "snapshot" : false
}
```

## List all CM users
```bash
[root@stf-btc-20171030-1 ~]# curl -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/api/v14/users"
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "sclairville",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```

## Report the database server in use by CM
```bash
[root@stf-btc-20171030-1 ~]# curl -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/api/v14/cm/scmDbInfo"
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```
