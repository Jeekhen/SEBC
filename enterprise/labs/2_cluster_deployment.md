'''

{
  "timestamp" : "2016-12-07T16:41:33.606Z",
  "clusters" : [ {
    "name" : "Jeekhen_Cluster",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "472907776"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "472907776"
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
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-14-159.ap-southeast-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-f5657d6ced72ce690dfd19e2ae54619c",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eqr9d5ufpehak69ekhv2b3ij2"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dl764yrx331grqeqfnl7t2xy"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "472907776"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-a509b698095408f930892ba2dab7fc1a",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "30c1c1f2-ee7a-47bc-8ac5-e5edb7914b40"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "61cvq0cn97h4ox5o1iyq4nqdh"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-b03573480f2f555a3ff7c7c01e7ef467",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "10485a04-a2c7-4f4d-b923-3f87a0832284"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4uuz2101qeradbvinuwioz7fx"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1al05bwv3hbzwuy30se39na"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-14-158.ap-southeast-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "secretpassword"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-d4d1cb12a11fb7630a1710048d3de34d"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-f5657d6ced72ce690dfd19e2ae54619c",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "buoj8xfjv1kysi46phzyc8g2j"
          }, {
            "name" : "secret_key",
            "value" : "60T8tZpTlcCgNjV3Fh4f9vLeeHvCzj"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-14-158.ap-southeast-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
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
        "name" : "oozie-OOZIE_SERVER-f5657d6ced72ce690dfd19e2ae54619c",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9dn1iol0302yopz4a2noecppf"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "472907776"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "node_manager_java_heapsize",
            "value" : "472907776"
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
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1024"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "472907776"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4939"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "4"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "q2oIvLAUMsQnSD2MQZKHW4DItfukk6"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5y1kfgf8h1h1nx0pu177irfrg"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-a509b698095408f930892ba2dab7fc1a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "30c1c1f2-ee7a-47bc-8ac5-e5edb7914b40"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6bycpw5epm71ylyklnhgm7t4d"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-b03573480f2f555a3ff7c7c01e7ef467",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "10485a04-a2c7-4f4d-b923-3f87a0832284"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "72ems36oski389sctym849maj"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-bd8960285c9b53487438a30493a99f43",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "934d8274-e676-4d67-b117-599f449078b0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "31o8xfe7tbza76462olv9zv7u"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ekiosbhmh7jkt1kno1ny6414a"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-f5657d6ced72ce690dfd19e2ae54619c",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2y9sy2hmrfnjyjtjqlck1pryx"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "47"
          }, {
            "name" : "role_jceks_password",
            "value" : "a0b0978h8vihv3c8y34rzj017"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "472907776"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "472907776"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3219965132"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "614465536"
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
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_handler_count",
            "value" : "32"
          }, {
            "name" : "dfs_namenode_service_handler_count",
            "value" : "32"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "472907776"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "u7ZoQQj1sSoYX8T8J9oF2TloR0tMtV"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "q7UtYyOWUjaskieSmfr0Geerum3Xly"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "Fh6vpST8EYfiacCD6eN6qRQ56ilSfR"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "service_config_suppression_nameservice_namenodes_heap_size_validator",
          "value" : "true"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-a509b698095408f930892ba2dab7fc1a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "30c1c1f2-ee7a-47bc-8ac5-e5edb7914b40"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5i2m3ed0bhce4erx37ha1edgk"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-b03573480f2f555a3ff7c7c01e7ef467",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "10485a04-a2c7-4f4d-b923-3f87a0832284"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9dt8oatprjutphxqoq5y8459d"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-bd8960285c9b53487438a30493a99f43",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "934d8274-e676-4d67-b117-599f449078b0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eymjqpr1i8kiebdp7ba02itz3"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3mgy9gx3tokno2mzwnzhjjyoy"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-f5657d6ced72ce690dfd19e2ae54619c",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8vjcb60k7h2qgrmgwfi877s6u"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6zd4bbyxfmwd42mj7wzk64rch"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-f5657d6ced72ce690dfd19e2ae54619c",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bos1uuba9mcgj3llqfxb9g9e7"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-b03573480f2f555a3ff7c7c01e7ef467",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "10485a04-a2c7-4f4d-b923-3f87a0832284"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e937bq1ma2xhml5sh5c0xfq77"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dampqonqxatzumh764rmtmvac"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-f5657d6ced72ce690dfd19e2ae54619c",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9qlo7gv9pwzqx6ri0gbtozvsj"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-d4d1cb12a11fb7630a1710048d3de34d",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-425697e5"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "49"
          }, {
            "name" : "role_jceks_password",
            "value" : "cii3gw99i0lyhx9lhvqsfeas8"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-f5657d6ced72ce690dfd19e2ae54619c",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "57"
          }, {
            "name" : "role_jceks_password",
            "value" : "1x0eaf25igmlsz4lnjqnqe6z5"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "5fc18e5b-132d-4f2a-a630-dce1c9b8f06b",
    "ipAddress" : "172.31.14.158",
    "hostname" : "ip-172-31-14-158.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-425697e5",
    "ipAddress" : "172.31.14.159",
    "hostname" : "ip-172-31-14-159.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "10485a04-a2c7-4f4d-b923-3f87a0832284",
    "ipAddress" : "172.31.14.160",
    "hostname" : "ip-172-31-14-160.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "30c1c1f2-ee7a-47bc-8ac5-e5edb7914b40",
    "ipAddress" : "172.31.14.161",
    "hostname" : "ip-172-31-14-161.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "934d8274-e676-4d67-b117-599f449078b0",
    "ipAddress" : "172.31.14.162",
    "hostname" : "ip-172-31-14-162.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-d4d1cb12a11fb7630a1710048d3de34d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e828a06d3944b6b33bcd93ce8cd26dba5dfb2324bc6d2a1f3cb5916f77553ecd",
    "pwSalt" : 4663031672731444275,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-d4d1cb12a11fb7630a1710048d3de34d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "274a791a3f74786de4c0757f71371306a9bffef5ec0c23b1a3c50c9701b3f833",
    "pwSalt" : 8225274003537431900,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-d4d1cb12a11fb7630a1710048d3de34d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "1e4f943e355def44daaf5fe65e0b1c0eedf29fca67c61f5db5da906c1539c41e",
    "pwSalt" : 194667792397583861,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-d4d1cb12a11fb7630a1710048d3de34d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "654ac7ca9cb8b369e825f7b4933c0e454d360e0f08ae8d400be36c6d3a137d7b",
    "pwSalt" : 1109283470039879992,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-d4d1cb12a11fb7630a1710048d3de34d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ec0255969d9a72c1348bb4e01ef32581e152843858d5b9090a8de6bdaa20cc0d",
    "pwSalt" : -7111002803089757463,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "9aa0df919199d56b714437d4cca61f1f9d80de0f206bde21844250d869470bf9",
    "pwSalt" : 3604287862984082258,
    "pwLogin" : true
  }, {
    "name" : "jeekhen",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "811694915c6d9b545ded01f7f961c84343bbc60e72547b63bfa89b10c3a6b940",
    "pwSalt" : -8663846416974815652,
    "pwLogin" : true
  }, {
    "name" : "minotaur ",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "84c5719b560535ef219e73ef61ef00aa700ead2f41aba01c9197592d792c25d0",
    "pwSalt" : 4293242336297301786,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20160916-1419",
    "gitHash" : "d23c620f3a3bbd85d8511d6ebba49beaaab14b75",
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
          "value" : "ip-172-31-14-159.ap-southeast-1.compute.internal"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "amon_password"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        }, {
          "name" : "firehose_heapsize",
          "value" : "472907776"
        } ]
      }, {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "472907776"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "472907776"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        }, {
          "name" : "role_config_suppression_firehose_heap_size_validator",
          "value" : "true"
        }, {
          "name" : "role_config_suppression_firehose_non_java_memory_validator",
          "value" : "true"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-14-159.ap-southeast-1.compute.internal"
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
          "value" : "472907776"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "472907776"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        }, {
          "name" : "role_config_suppression_firehose_heap_size_validator",
          "value" : "true"
        }, {
          "name" : "role_config_suppression_firehose_non_java_memory_validator",
          "value" : "true"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-d4d1cb12a11fb7630a1710048d3de34d",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "i-425697e5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dcgfhtv9is94ke428fas4daay"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-d4d1cb12a11fb7630a1710048d3de34d",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-425697e5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "38gqdhki49q6i3o4uj80ck0n7"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-d4d1cb12a11fb7630a1710048d3de34d",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-425697e5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dxxr2pnt0l495rn4dyemz2kjv"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-d4d1cb12a11fb7630a1710048d3de34d",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-425697e5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9lacfo5caczh7ert6tj6vtlhk"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-d4d1cb12a11fb7630a1710048d3de34d",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-425697e5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bxo07ney9c9tmn13anuj33z21"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-d4d1cb12a11fb7630a1710048d3de34d",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-425697e5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2z420zc54d22y6nehdb6u5y63"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/21/2012 22:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh5/parcels/5.8.2/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}

'''