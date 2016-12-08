Show Hive Status

```
curl -u jeekhen:cloudera http://master:7180/api/v2/clusters/Jeekhen_Cluster/services/hive
```

Stop Hive Service

```
curl -X POST -u jeekhen:cloudera http://master:7180/api/v2/clusters/Jeekhen_Cluster/services/hive/commands/stop

```

Start Hive Service

```
curl -X POST -u jeekhen:cloudera http://master:7180/api/v2/clusters/Jeekhen_Cluster/services/hive/commands/start

```