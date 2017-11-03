## Enterprise lab 

**Use the API**
```
export CM_USER=sclairville
export CM_PASS=cloudera

[root@stf-btc-20171030-1 ~]# curl -u $CM_USER:$CM_PASS 'http://stf-btc-20171030-1.gce.cloudera.com:7180/api/v2/cm/deployment' > 2_cluster_deployment.md
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 38705    0 38705    0     0   740k      0 --:--:-- --:--:-- --:--:--  755k
```
```
[root@stf-btc-20171030-1 ~]# cat 2_cluster_deployment.md

```
```javascript

{
  "timestamp" : "2017-11-03T01:27:26.323Z",
  "clusters" : [ {
    "name" : "Boomerang",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "608174080"
          } ]
        } ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-4c3797694576559187e2b294ea217dd6",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "rws4o8uq1288krynj6xv7pi9"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-96ac33274dd25378507265305abb1d19",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9vrbvlcfq82aqvptp0q5h1h61"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-b7769bd45d188ef180771e9723ac82ca",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9hdl1te8sdj9yhge5y89rfmpk"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "stf-btc-20171030-1.gce.cloudera.com"
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
            "value" : "608174080"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-4c3797694576559187e2b294ea217dd6",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "76t5alvpetfr4nkmg809aeajz"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "stf-btc-20171030-1.gce.cloudera.com"
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
          "value" : "hdfs-HTTPFS-073bd1705f5621b320bfbd23b7f1b5af"
        }, {
          "name" : "impala_service",
          "value" : "impala"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3yqi98lsr2u9h6zihoex9sf8q"
          }, {
            "name" : "secret_key",
            "value" : "H2GIkChOCvrZuaCbburwxX3RLCGLzY"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5vtrgnvnvfomqn5z9iancgkzn"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn1"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10736126771"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn1"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn1"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "8Vg3VdExJPxmeAV5keJ7DfEBW9VxPi"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "KflHUMriS9YwOb4MTWnnHUy2acUwE4"
        }, {
          "name" : "hadoop_secure_web_ui",
          "value" : "true"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "Wuwdu018M67YpergNDwcQYC9eXeSm7"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-b7769bd45d188ef180771e9723ac82ca",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "89azq0sm9fc8a0gu2kucdtas8"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-91c6cc112d798f1fc4ad1576df630a0a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cdoi1xv0kx858dzikqszamj34"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-96ac33274dd25378507265305abb1d19",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "80gbl0doaf3bnvpjnx3ger0ix"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-b7769bd45d188ef180771e9723ac82ca",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "tcgnajrsa9avytg278hgs38f"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-4c3797694576559187e2b294ea217dd6",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "50v4xf166hwqh05gtty9clatf"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-96ac33274dd25378507265305abb1d19",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1dtyp21b75af1oqmscz0dzos6"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e7s4we6zddkaqsq3bi12q9ywb"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-4c3797694576559187e2b294ea217dd6",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3tq0of2wtnhyfv5gf073jyog6"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-96ac33274dd25378507265305abb1d19",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "awqb7utxryobpag5j83vu4q9s"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-b7769bd45d188ef180771e9723ac82ca",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4iiqatt9v6r0cbbzinl8t5u8h"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-4c3797694576559187e2b294ea217dd6",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "boomerangha"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "boomerangha"
          }, {
            "name" : "namenode_id",
            "value" : "131"
          }, {
            "name" : "role_jceks_password",
            "value" : "c9iuevc6gijzpybdzov7pr8z3"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-96ac33274dd25378507265305abb1d19",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "boomerangha"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "boomerangha"
          }, {
            "name" : "namenode_id",
            "value" : "171"
          }, {
            "name" : "role_jceks_password",
            "value" : "8uh54fjke6p1rs9z5gccm5ijw"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "4"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "608174080"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1600"
          }, {
            "name" : "rm_io_weight",
            "value" : "800"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm1"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "1"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1167"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "608174080"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "1167"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "1"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "Q7X3PihxAHuprNH9xxhDHG0AtPFfhZ"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-4c3797694576559187e2b294ea217dd6",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "474rg4aadflfatxh0w8mvj9q3"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3httq4lrh8jfs9wqcelscpa27"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-91c6cc112d798f1fc4ad1576df630a0a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "50hm4k86vea1s6zace1ame469"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-96ac33274dd25378507265305abb1d19",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2m0rryx4h0rs331wv07uxt04f"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-b7769bd45d188ef180771e9723ac82ca",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9w3lnnd0pvdkfw9lwrvrp27qt"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-4c3797694576559187e2b294ea217dd6",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "138"
          }, {
            "name" : "role_jceks_password",
            "value" : "6rvhlw2d19q8l63q64m604wec"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_enable_db_notification",
            "value" : "true"
          }, {
            "name" : "hive_metastore_java_heapsize",
            "value" : "1369440256"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "136944025"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_java_heapsize",
            "value" : "608174080"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "6"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "1513409740"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "254"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "stf-btc-20171030-1.gce.cloudera.com"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "hive_service_config_safety_valve",
          "value" : "<property><name>hive.server2.authentication</name><value>KERBEROS</value></property><property><name>hive.server2.authentication.kerberos.principal</name><value>hive/_HOST@STEFUN.COM</value></property><property><name>hive.stats.ndv.error</name><value>5.0</value></property>"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "spark_on_yarn_service",
          "value" : "none"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-4c3797694576559187e2b294ea217dd6",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-91c6cc112d798f1fc4ad1576df630a0a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-96ac33274dd25378507265305abb1d19",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-b7769bd45d188ef180771e9723ac82ca",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-b7769bd45d188ef180771e9723ac82ca",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4utn7tzdxxugvk39z2oidgeix"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-4c3797694576559187e2b294ea217dd6",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ep80s5sta9hri27c3jlvzldmc"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SENTRY_SERVER",
          "items" : [ {
            "name" : "sentry_server_java_heapsize",
            "value" : "268435456"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "stf-btc-20171030-1.gce.cloudera.com"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,hdfs,sclairville,impala,hue,solr,kafka"
        }, {
          "name" : "sentry_service_allow_connect",
          "value" : "hive,sclairville,impala,hue,hdfs,solr,kafka"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-4c3797694576559187e2b294ea217dd6",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "0f2a406f-a6fa-4aa8-aea0-baec70e6cc98"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-91c6cc112d798f1fc4ad1576df630a0a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-96ac33274dd25378507265305abb1d19",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-b7769bd45d188ef180771e9723ac82ca",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7608k29dxawzia9j32iz108v0"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    }, {
      "name" : "impala",
      "type" : "IMPALA",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "CATALOGSERVER",
          "items" : [ {
            "name" : "catalogd_embedded_jvm_heapsize",
            "value" : "52428800"
          } ]
        }, {
          "roleType" : "IMPALAD",
          "items" : [ {
            "name" : "impalad_memory_limit",
            "value" : "268435456"
          }, {
            "name" : "scratch_dirs",
            "value" : "/impala/impalad"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "llama_am_ha_zk_auth_secret_key",
          "value" : "X4swT0iiQbtRjYH4wWQOuGBZq93Lpq"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        } ]
      },
      "roles" : [ {
        "name" : "impala-CATALOGSERVER-91c6cc112d798f1fc4ad1576df630a0a",
        "type" : "CATALOGSERVER",
        "hostRef" : {
          "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2prkei7g80jq926sbcgxtqjol"
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-073bd1705f5621b320bfbd23b7f1b5af",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cyqc7b8xqp2hg6tft6cwetget"
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-91c6cc112d798f1fc4ad1576df630a0a",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5z6eexjlb66e9taao4t8vrllv"
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-96ac33274dd25378507265305abb1d19",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "e17ed2cb-fadd-4dab-b63d-fea6f8acea85"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ad3wixw5uia91z30yo08ibf3p"
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-b7769bd45d188ef180771e9723ac82ca",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8890tuc5g7lwwgrxvt930cqsd"
          } ]
        }
      }, {
        "name" : "impala-STATESTORE-b7769bd45d188ef180771e9723ac82ca",
        "type" : "STATESTORE",
        "hostRef" : {
          "hostId" : "edc2e8c5-5fca-4b4a-bd8e-00f3ebaf43ec"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "be82731c7wk10mpzo80o5le7z"
          } ]
        }
      } ],
      "displayName" : "Impala"
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
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__3fd3604e-ef30-4f4e-ab90-7b2150356883",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ad473a630487c39ac725e5b758c0422b4356bbd1599b0fecd86a40d00f0c454c",
    "pwSalt" : -9125322469030345126,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__b32a9560-51e5-4e6e-9df3-87e9bcaf2c55",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e38a0b73a7eb0629ab0b786149acb9d7232a01d931b6b271e4d11ad40a46d03b",
    "pwSalt" : 2197226874092935092,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-4c3797694576559187e2b294ea217dd6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "53a9d4fec5ff69a756e61e08ceddccf58166920d5c120bb26f186afad584447b",
    "pwSalt" : -2603840785669112624,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-91c6cc112d798f1fc4ad1576df630a0a",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "acbbc734a6baa25100d1bcd8f88a4ec696da8fb458c9a9b914ff9c4e53188586",
    "pwSalt" : -3091183866676028945,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-073bd1705f5621b320bfbd23b7f1b5af",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "94b2ffc45bd665efa994a8584cdc0ab1939fe613c1086c986720a61816000ef7",
    "pwSalt" : 5774105663712586798,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-4c3797694576559187e2b294ea217dd6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "f955d9a5fc403b2331db9b94f549e5f68ac3b1baa1578dc0bd3bc5dc40b79e13",
    "pwSalt" : -9103162715527474285,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-4c3797694576559187e2b294ea217dd6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a34fdd19ab3ecf288244069f06e9b1ef4b2703d608b216c43b99b14175178dc5",
    "pwSalt" : 2453017886414085651,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-91c6cc112d798f1fc4ad1576df630a0a",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "99b1ad4d835e69782275dc7a86e78f956f68cc26096e6daee142c9c9fd3961d2",
    "pwSalt" : 5133990582879514596,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-073bd1705f5621b320bfbd23b7f1b5af",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3feec111b6d43637a1b428ae7fa972b42fc39b4d391ca3fbf915ca2f3bc5edba",
    "pwSalt" : -5003534403522625244,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-4c3797694576559187e2b294ea217dd6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "670d79734a73c088c8858657c63c9ec579f18e17f037bbe0630914de7793a18b",
    "pwSalt" : -938940155172891492,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-4c3797694576559187e2b294ea217dd6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "32781d6000660fe2dd2e8060f764e487149ad3c34b72ad2586bd531abd6ad66c",
    "pwSalt" : -7724159297461483407,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-91c6cc112d798f1fc4ad1576df630a0a",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "13c4dc757e04c817d3adc2d4e41f761b318244848edef5ad89b0a4aeb87dbeb8",
    "pwSalt" : -5661740310182522608,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "75caada4bd7c4fd201784563030804a913a8e8fa069ab1759a0328f501f01066",
    "pwSalt" : 8540526919083413645,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "aa3aaabf0e7f118df6b950d5556a7db09cb2aed5fd57075487f8d1cc5323c50d",
    "pwSalt" : -244581848263818942,
    "pwLogin" : true
  }, {
    "name" : "sclairville",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "35bd0bac9169aeac6e6a141cc2ca27b3e761081a118e6bf2a41f064bf900b794",
    "pwSalt" : 1735389803320903014,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.9.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170627-1506",
    "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "ACTIVITYMONITOR",
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "stf-btc-20171030-1.gce.cloudera.com"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "amon_password"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        } ]
      }, {
        "roleType" : "ALERTPUBLISHER",
        "items" : [ {
          "name" : "alert_mailserver_password",
          "value" : "cloudera"
        } ]
      }, {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "608174080"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "1610612736"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "stf-btc-20171030-1.gce.cloudera.com"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "608174080"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "1610612736"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-91c6cc112d798f1fc4ad1576df630a0a",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "310g9ffulpftesjgpip6m7epc"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-073bd1705f5621b320bfbd23b7f1b5af",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4ov6t7hupb34sfh87c2ee31at"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-073bd1705f5621b320bfbd23b7f1b5af",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1ml25w9oc5af7fnqh6s5kim9s"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-91c6cc112d798f1fc4ad1576df630a0a",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4yalp07zp7wzhjmybkmglh02m"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-073bd1705f5621b320bfbd23b7f1b5af",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "e58e728b-c25a-40c8-84a3-b9f05fc35f0d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6bxnay84tvsti4jijw8hvww9n"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-91c6cc112d798f1fc4ad1576df630a0a",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "ec8b2e68-0881-4bf7-a4a9-e9f9a3ec301e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "t3clt4s5lkfz0uddz6a2y8m6"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/27/2012 0:00"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA9AAEAClNURUZVTi5DT00ADGNsb3VkZXJhLXNjbQAAAAFZ+2nTAQAXABDkjJL+JMjHMmRA1ucsjMWZAAAAAQ=="
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@STEFUN.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "stf-btc-20171030-5.gce.cloudera.com"
    }, {
      "name" : "KRB_ENC_TYPES",
      "value" : "arcfour-hmac"
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true"
    }, {
      "name" : "MAX_RENEW_LIFE",
      "value" : "604800"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "NOT_ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://stf-btc-20171030-1.gce.cloudera.com/spark2/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "STEFUN.COM"
    } ]
  }
}
```
