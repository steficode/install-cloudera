## curl Statements API
```
Define the variables for the CM_Server API

CMS_URL=http://stf-btc-20171030-1.gce.cloudera.com
CMS_PORT=7180
CMS_PATH_SERVICES=api/v1/clusters/Boomerang/services
CM_USER=sclairville
CM_PASS=cloudera


** > Stop Hive**

[root@stf-btc-20171030-1 ~]# curl -X POST -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/$CMS_PATH_SERVICES/hive/commands/stop"
{
  "id" : 2045,
  "name" : "Stop",
  "startTime" : "2017-11-03T05:47:54.382Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster2",
    "serviceName" : "hive"
 }

[root@stf-btc-20171030-1 ~]# curl -su $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/$CMS_PATH_SERVICES/hive/"| grep --color 'serviceState'
  "serviceState" : "STOPPED",

  The hive Service is correctly **STOPPED** after the double check.

** > Start Hive**

[root@stf-btc-20171030-1 ~]# curl -X POST -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/$CMS_PATH_SERVICES/hive/commands/start"
{
  "id" : 2052,
  "name" : "Start",
  "startTime" : "2017-11-03T05:48:54.068Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster2",
    "serviceName" : "hive"
  }
}

[root@stf-btc-20171030-1 ~]# curl -su $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/$CMS_PATH_SERVICES/hive/"| grep --color 'serviceState'
  "serviceState" : "STARTED",

The service Hive is correctly **STARTED** after the double check
 

** > Check the status of Hive service**

[root@stf-btc-20171030-1 ~]# curl -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/$CMS_PATH_SERVICES/hive/"| grep --color 'serviceState'
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   440    0   440    0     0  20445      0 --:--:-- --:--:-- --:--:-- 20952
  "serviceState" : "STARTED",

```
