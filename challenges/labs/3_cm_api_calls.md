* The command and output from the CM API call `../api/v5/hosts`

**Use the API**
```
export CM_USER=admin
export CM_PASS=admin
export CMS_URL=http://stf-btc-challenge-2.gce.cloudera.com
export CMS_PORT=7180
```
```json
[root@stf-btc-challenge-2 ~]# curl -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/api/v5/hosts"

{
  "items" : [ {
    "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98",
    "ipAddress" : "172.31.120.135",
    "hostname" : "stf-btc-20171030-1.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/0f2a406f-a6fa-4aa8-aea0-baec70e6cc98",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13656707072
  }, {
    "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85",
    "ipAddress" : "172.31.120.137",
    "hostname" : "stf-btc-20171030-2.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/e17ed2cb-fadd-4dab-b63d-fea6f8acea85",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13656707072
  }, {
    "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec",
    "ipAddress" : "172.31.120.138",
    "hostname" : "stf-btc-20171030-3.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13656707072
  }, {
    "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d",
    "ipAddress" : "172.31.120.160",
    "hostname" : "stf-btc-20171030-4.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/e58e728b-c25a-40c8-84a3-b9f05fc35f0d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13656707072
  }, {
    "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e",
    "ipAddress" : "172.31.120.161",
    "hostname" : "stf-btc-20171030-5.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13656707072
  }, {
    "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c",
    "ipAddress" : "172.31.118.148",
    "hostname" : "stf-btc-challenge-1.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13685518336
  }, {
    "hostId" : "36a2d5c5-b066-4d54-b947-37baae81a7cc",
    "ipAddress" : "172.31.118.147",
    "hostname" : "stf-btc-challenge-2.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/36a2d5c5-b066-4d54-b947-37baae81a7cc",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13685518336
  }, {
    "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba",
    "ipAddress" : "172.31.118.157",
    "hostname" : "stf-btc-challenge-3.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/e670f7a0-e1a7-43b3-8d02-8f315b3e29ba",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13685518336
  }, {
    "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f",
    "ipAddress" : "172.31.118.158",
    "hostname" : "stf-btc-challenge-4.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/e5dce8fe-2a3b-4feb-bff1-0659498e252f",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13685518336
  }, {
    "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa",
    "ipAddress" : "172.31.118.166",
    "hostname" : "stf-btc-challenge-5.gce.cloudera.com",
    "rackId" : "/default",
    "hostUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/hostRedirect/072e06d9-6417-4222-80af-f7b4936f10aa",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "totalPhysMemBytes" : 13685518336
  } ]
}[
```

* The command and output from the CM API call `../api/v11/clusters/<githubName>/services`
```json
[root@stf-btc-challenge-2 ~]# curl -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/api/v11/clusters/challengy/services"
{
  "items" : [ {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/zookeeper",
    "roleInstancesUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/zookeeper/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/oozie",
    "roleInstancesUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/oozie/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/hue",
    "roleInstancesUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/hue/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HUE_LOAD_BALANCER_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/spark_on_yarn",
    "roleInstancesUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/spark_on_yarn/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "SPARK_ON_YARN_SPARK_ON_YARN_SPARK_YARN_HISTORY_SERVER_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/hdfs",
    "roleInstancesUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/hdfs/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/yarn",
    "roleInstancesUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/yarn/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/hive",
    "roleInstancesUrl" : "http://stf-btc-challenge-2.gce.cloudera.com:7180/cmf/serviceRedirect/hive/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HIVE_WEBHCATS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive",
    "entityStatus" : "GOOD_HEALTH"
  } ]
}
```

    * The command and output for your CM deployment (yes, again)
```json
[root@stf-btc-challenge-2 ~]# curl -u $CM_USER:$CM_PASS "$CMS_URL:$CMS_PORT/api/v11/cm/deployment"
{
  "timestamp" : "2017-11-04T04:31:53.076Z",
  "clusters" : [ {
    "name" : "cluster",
    "displayName" : "challengy",
    "version" : "CDH5",
    "fullVersion" : "5.8.5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "blupn8a5r6eun1acz7mhs5tv"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      }, {
        "name" : "zookeeper-SERVER-46afe95394e4bfd7e23cb3ba4b02c267",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1kjuxqca7o1rhjz2b6srwim4a"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      }, {
        "name" : "zookeeper-SERVER-cc4476900f61232a5387869c07370c61",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cmj8dtgfg3sm4tln73z0az084"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      } ],
      "displayName" : "ZooKeeper",
      "roleConfigGroups" : [ {
        "name" : "zookeeper-SERVER-BASE",
        "displayName" : "Server Default Group",
        "roleType" : "SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "zookeeper"
        },
        "config" : {
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "738197504"
          } ]
        }
      } ]
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "spark_on_yarn_service",
          "value" : "spark_on_yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1cfy3rdmfto98avksv0qvrrzy"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "oozie-OOZIE_SERVER-BASE"
        }
      } ],
      "displayName" : "Oozie",
      "roleConfigGroups" : [ {
        "name" : "oozie-OOZIE_SERVER-BASE",
        "displayName" : "Oozie Server Default Group",
        "roleType" : "OOZIE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "oozie"
        },
        "config" : {
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "stf-btc-challenge-1.gce.cloudera.com"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "966787072"
          } ]
        }
      } ]
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "items" : [ {
          "name" : "database_host",
          "value" : "stf-btc-challenge-1.gce.cloudera.com"
        }, {
          "name" : "database_password",
          "value" : "hue_password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-6a10a6f97604b5831953d619b46aac41"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-f88414b9b82ead6beb58d0bb10d1e6ff",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "36a2d5c5-b066-4d54-b947-37baae81a7cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1hkcx0xm2gonyza9t5ppcuv46"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_LOAD_BALANCER-BASE"
        }
      }, {
        "name" : "hue-HUE_SERVER-46afe95394e4bfd7e23cb3ba4b02c267",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8pe9ug36ak9cb6zyb1slq92ip"
          }, {
            "name" : "secret_key",
            "value" : "0USIFp2JLA25qBJAWI6ebw6lM9S7dJ"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
        }
      }, {
        "name" : "hue-HUE_SERVER-cc4476900f61232a5387869c07370c61",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "77jbcx6cfm9yoroxzfhu493yr"
          }, {
            "name" : "secret_key",
            "value" : "qcMePkPJj5XjJMcxEXa9LlKRmZ5n8X"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
        }
      } ],
      "displayName" : "Hue",
      "roleConfigGroups" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-BASE",
        "displayName" : "Load Balancer Default Group",
        "roleType" : "HUE_LOAD_BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-HUE_SERVER-BASE",
        "displayName" : "Hue Server Default Group",
        "roleType" : "HUE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-KT_RENEWER-BASE",
        "displayName" : "Kerberos Ticket Renewer Default Group",
        "roleType" : "KT_RENEWER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "spark_on_yarn",
      "type" : "SPARK_ON_YARN",
      "config" : {
        "items" : [ {
          "name" : "yarn_service",
          "value" : "yarn"
        } ]
      },
      "roles" : [ {
        "name" : "spar40365358-SPARK_YARN_HISTORY_SERVER-2acdeb2a656a4a4332dcecafe",
        "type" : "SPARK_YARN_HISTORY_SERVER",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9aipblf4m6d2o1r7o0ih2ws8f"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "spark_on_yarn-SPARK_YARN_HISTORY_SERVER-BASE"
        }
      }, {
        "name" : "spark_on_yarn-GATEWAY-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "spark_on_yarn-GATEWAY-BASE"
        }
      }, {
        "name" : "spark_on_yarn-GATEWAY-46afe95394e4bfd7e23cb3ba4b02c267",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "spark_on_yarn-GATEWAY-BASE"
        }
      }, {
        "name" : "spark_on_yarn-GATEWAY-6a10a6f97604b5831953d619b46aac41",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "spark_on_yarn-GATEWAY-BASE"
        }
      }, {
        "name" : "spark_on_yarn-GATEWAY-cc4476900f61232a5387869c07370c61",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "spark_on_yarn-GATEWAY-BASE"
        }
      }, {
        "name" : "spark_on_yarn-GATEWAY-f88414b9b82ead6beb58d0bb10d1e6ff",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "36a2d5c5-b066-4d54-b947-37baae81a7cc"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "spark_on_yarn-GATEWAY-BASE"
        }
      } ],
      "displayName" : "Spark",
      "roleConfigGroups" : [ {
        "name" : "spark_on_yarn-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "spark_on_yarn"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "spark_on_yarn-SPARK_YARN_HISTORY_SERVER-BASE",
        "displayName" : "History Server Default Group",
        "roleType" : "SPARK_YARN_HISTORY_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "spark_on_yarn"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "MtaKJECPUbVnWOKOW06FIXCznno3jn"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "yBZEk1uzJJOR2EFAC8A7pFay0HDjaW"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "I6305Pgfj0vGhkNc5tl6Id7IAH1QwI"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-6a10a6f97604b5831953d619b46aac41",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-BALANCER-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8w9fral0951uws17hhlf74q42"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-2"
        }
      }, {
        "name" : "hdfs-DATANODE-46afe95394e4bfd7e23cb3ba4b02c267",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "73ei3tyjqvytvvp5oibtnqug2"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-1"
        }
      }, {
        "name" : "hdfs-DATANODE-cc4476900f61232a5387869c07370c61",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1zxrv5ncy0cnu4uoi97z23ria"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-3"
        }
      }, {
        "name" : "hdfs-DATANODE-f88414b9b82ead6beb58d0bb10d1e6ff",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "36a2d5c5-b066-4d54-b947-37baae81a7cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "563h1lc5fiook1u9o9vyfmau9"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-6a10a6f97604b5831953d619b46aac41",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c"
        },
        "config" : {
          "items" : [ {
            "name" : "namenode_id",
            "value" : "104"
          }, {
            "name" : "role_jceks_password",
            "value" : "9438c3e9a0o7s7mxrb552c2nh"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-f88414b9b82ead6beb58d0bb10d1e6ff",
        "type" : "SECONDARYNAMENODE",
        "hostRef" : {
          "hostId" : "36a2d5c5-b066-4d54-b947-37baae81a7cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cnnla4nkzda8o66ia9xuqvkut"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-SECONDARYNAMENODE-BASE"
        }
      } ],
      "displayName" : "HDFS",
      "roleConfigGroups" : [ {
        "name" : "hdfs-BALANCER-BASE",
        "displayName" : "Balancer Default Group",
        "roleType" : "BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-1",
        "displayName" : "DataNode Group 1",
        "roleType" : "DATANODE",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "738197504"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10555276902"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "960495616"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-2",
        "displayName" : "DataNode Group 2",
        "roleType" : "DATANODE",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "966787072"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10555276902"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "1257242624"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-3",
        "displayName" : "DataNode Group 3",
        "roleType" : "DATANODE",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10555276902"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "2507145216"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-BASE",
        "displayName" : "DataNode Default Group",
        "roleType" : "DATANODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10555276902"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "2717908992"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-BASE",
        "displayName" : "Failover Controller Default Group",
        "roleType" : "FAILOVERCONTROLLER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-BASE",
        "displayName" : "HttpFS Default Group",
        "roleType" : "HTTPFS",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-BASE",
        "displayName" : "JournalNode Default Group",
        "roleType" : "JOURNALNODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-NAMENODE-BASE",
        "displayName" : "NameNode Default Group",
        "roleType" : "NAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-BASE",
        "displayName" : "NFS Gateway Default Group",
        "roleType" : "NFSGATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-BASE",
        "displayName" : "SecondaryNameNode Default Group",
        "roleType" : "SECONDARYNAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          } ]
        }
      } ],
      "replicationSchedules" : [ ],
      "snapshotPolicies" : [ ]
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "OD2l8v9F3S9b0PnfkurEvnQo9QMEey"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-6a10a6f97604b5831953d619b46aac41",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7ewvkyrr7bikca9ihrzz3eri"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-JOBHISTORY-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dnzbc0x3y7i0shs5dv2dt86fs"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-2"
        }
      }, {
        "name" : "yarn-NODEMANAGER-46afe95394e4bfd7e23cb3ba4b02c267",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "vfpf3vap1b5fo4601qbffakt"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-1"
        }
      }, {
        "name" : "yarn-NODEMANAGER-cc4476900f61232a5387869c07370c61",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "77h25uez2y9i24dhi4lfszf8c"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-3"
        }
      }, {
        "name" : "yarn-NODEMANAGER-f88414b9b82ead6beb58d0bb10d1e6ff",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "36a2d5c5-b066-4d54-b947-37baae81a7cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "54vlemgu5ov0s1xypb6kpda9t"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-6a10a6f97604b5831953d619b46aac41",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "111"
          }, {
            "name" : "role_jceks_password",
            "value" : "6wx86j3isygsxhv7gmx8lu1vb"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-RESOURCEMANAGER-BASE"
        }
      } ],
      "displayName" : "YARN (MR2 Included)",
      "roleConfigGroups" : [ {
        "name" : "yarn-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "4"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-BASE",
        "displayName" : "JobHistory Server Default Group",
        "roleType" : "JOBHISTORY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-1",
        "displayName" : "NodeManager Group 1",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "node_manager_java_heapsize",
            "value" : "738197504"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "2"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1024"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2",
        "displayName" : "NodeManager Group 2",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "node_manager_java_heapsize",
            "value" : "966787072"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "2"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1199"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-3",
        "displayName" : "NodeManager Group 3",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "2"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2391"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-BASE",
        "displayName" : "NodeManager Default Group",
        "roleType" : "NODEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "2"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2592"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-BASE",
        "displayName" : "ResourceManager Default Group",
        "roleType" : "RESOURCEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "2592"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "2"
          } ]
        }
      } ]
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "stf-btc-challenge-1.gce.cloudera.com"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "spark_on_yarn_service",
          "value" : "spark_on_yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-46afe95394e4bfd7e23cb3ba4b02c267",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-6a10a6f97604b5831953d619b46aac41",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-cc4476900f61232a5387869c07370c61",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-f88414b9b82ead6beb58d0bb10d1e6ff",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "36a2d5c5-b066-4d54-b947-37baae81a7cc"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-HIVEMETASTORE-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "47xkrw16q56euqwyag1w8xcl5"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-1"
        }
      }, {
        "name" : "hive-HIVEMETASTORE-46afe95394e4bfd7e23cb3ba4b02c267",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4gqarwywco9tccl85fxn6p762"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-BASE"
        }
      }, {
        "name" : "hive-HIVESERVER2-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cwcpyn8ddg8ef7bwqq73hz7r9"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVESERVER2-BASE"
        }
      }, {
        "name" : "hive-HIVESERVER2-6a10a6f97604b5831953d619b46aac41",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "kf2nbvf6ecksohe4w7msnjrh"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVESERVER2-1"
        }
      }, {
        "name" : "hive-WEBHCAT-2acdeb2a656a4a4332dcecafea6c7d5a",
        "type" : "WEBHCAT",
        "hostRef" : {
          "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_webhcat_secret_key",
            "value" : "5wi6pNGVfeC3mVVnxX5oYo0QoOhC2e"
          }, {
            "name" : "role_jceks_password",
            "value" : "8m71ad88ds6qx17dq1i4nh5zw"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-WEBHCAT-BASE"
        }
      } ],
      "displayName" : "Hive",
      "roleConfigGroups" : [ {
        "name" : "hive-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-1",
        "displayName" : "Hive Metastore Server Group 1",
        "roleType" : "HIVEMETASTORE",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "966787072"
          } ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-BASE",
        "displayName" : "Hive Metastore Server Default Group",
        "roleType" : "HIVEMETASTORE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "738197504"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-1",
        "displayName" : "HiveServer2 Group 1",
        "roleType" : "HIVESERVER2",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "2496659456"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "912680550"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "153"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-BASE",
        "displayName" : "HiveServer2 Default Group",
        "roleType" : "HIVESERVER2",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "966787072"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "912680550"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "153"
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-BASE",
        "displayName" : "WebHCat Server Default Group",
        "roleType" : "WEBHCAT",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      } ],
      "replicationSchedules" : [ ]
    } ],
    "parcels" : [ {
      "product" : "CDH",
      "version" : "5.8.5-1.cdh5.8.5.p0.5",
      "stage" : "DISTRIBUTED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    }, {
      "product" : "CDH",
      "version" : "5.8.5-1.cdh5.8.5.p0.5",
      "stage" : "ACTIVATED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98",
    "ipAddress" : "172.31.120.135",
    "hostname" : "stf-btc-20171030-1.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85",
    "ipAddress" : "172.31.120.137",
    "hostname" : "stf-btc-20171030-2.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec",
    "ipAddress" : "172.31.120.138",
    "hostname" : "stf-btc-20171030-3.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d",
    "ipAddress" : "172.31.120.160",
    "hostname" : "stf-btc-20171030-4.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e",
    "ipAddress" : "172.31.120.161",
    "hostname" : "stf-btc-20171030-5.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "a63fd7de-01d8-4dd4-aad3-31ddb2b5d08c",
    "ipAddress" : "172.31.118.148",
    "hostname" : "stf-btc-challenge-1.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "36a2d5c5-b066-4d54-b947-37baae81a7cc",
    "ipAddress" : "172.31.118.147",
    "hostname" : "stf-btc-challenge-2.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "e670f7a0-e1a7-43b3-8d02-8f315b3e29ba",
    "ipAddress" : "172.31.118.157",
    "hostname" : "stf-btc-challenge-3.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f",
    "ipAddress" : "172.31.118.158",
    "hostname" : "stf-btc-challenge-4.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa",
    "ipAddress" : "172.31.118.166",
    "hostname" : "stf-btc-challenge-5.gce.cloudera.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-46afe95394e4bfd7e23cb3ba4b02c267",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "533fe6b6a78cf5c50e119596ca3bcff44f009466c8ba6f7c57eeb4a3f5162437",
    "pwSalt" : 7335156880570112792,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-46afe95394e4bfd7e23cb3ba4b02c267",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a60986661e3a0cceeb2203532d99371bf14672fd3629be1067ab6f1888897cc1",
    "pwSalt" : -2211095485988532839,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-cc4476900f61232a5387869c07370c61",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c163c70c0d0e34376884b2b3b339f9f8fadbe4ace987753c08df1c74801ceafe",
    "pwSalt" : -46783258274768554,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-46afe95394e4bfd7e23cb3ba4b02c267",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "74de61d52426ac736a28ea387c6b7c8cabd08c8a684007c34354ff713bf8f864",
    "pwSalt" : -3889763444676256118,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "2b191e383f7def1f67c7f4a811962beb6bf12510bfff1d1bbaa88a54265bcf21",
    "pwSalt" : -5366919070874935912,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.13.0",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20171002-1719",
    "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-cc4476900f61232a5387869c07370c61",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bt8adg2vdcewuzk6sdao1x7ay"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ALERTPUBLISHER-BASE"
      }
    }, {
      "name" : "mgmt-EVENTSERVER-46afe95394e4bfd7e23cb3ba4b02c267",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5qroqdm9rm4ym977kevvmwvlt"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-EVENTSERVER-BASE"
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-46afe95394e4bfd7e23cb3ba4b02c267",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bk022bqdara1nqvsitr9liq7"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-HOSTMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-cc4476900f61232a5387869c07370c61",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "072e06d9-6417-4222-80af-f7b4936f10aa"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7plx8qdk8o6sbvbhct0ybgqri"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-REPORTSMANAGER-BASE"
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-46afe95394e4bfd7e23cb3ba4b02c267",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "e5dce8fe-2a3b-4feb-bff1-0659498e252f"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "42nrp8geiua3270voj9u19ybh"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-SERVICEMONITOR-BASE"
      }
    } ],
    "displayName" : "Cloudera Management Service",
    "roleConfigGroups" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-BASE",
      "displayName" : "Activity Monitor Default Group",
      "roleType" : "ACTIVITYMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-BASE",
      "displayName" : "Alert Publisher Default Group",
      "roleType" : "ALERTPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-BASE",
      "displayName" : "Event Server Default Group",
      "roleType" : "EVENTSERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "738197504"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-BASE",
      "displayName" : "Host Monitor Default Group",
      "roleType" : "HOSTMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-NAVIGATOR-BASE",
      "displayName" : "Navigator Audit Server Default Group",
      "roleType" : "NAVIGATOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-NAVIGATORMETASERVER-BASE",
      "displayName" : "Navigator Metadata Server Default Group",
      "roleType" : "NAVIGATORMETASERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-BASE",
      "displayName" : "Reports Manager Default Group",
      "roleType" : "REPORTSMANAGER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "stf-btc-challenge-1.gce.cloudera.com"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-BASE",
      "displayName" : "Service Monitor Default Group",
      "roleType" : "SERVICEMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "6442450944"
        } ]
      }
    }, {
      "name" : "mgmt-TELEMETRYPUBLISHER-BASE",
      "displayName" : "Telemetry Publisher Default Group",
      "roleType" : "TELEMETRYPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    } ]
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 14:00"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "NOT_ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/5.12,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  },
  "allHostsConfig" : {
    "items" : [ ]
  },
  "peers" : [ ],
  "hostTemplates" : {
    "items" : [ ]
  }
}

```
