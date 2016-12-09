1) Command and output for hdfs dfs -ls /user
```
Found 6 items
drwxrwxrwx   - mapred hadoop              0 2016-12-08 21:47 /user/history
drwxrwxr-t   - hive   hive                0 2016-12-08 21:48 /user/hive
drwxrwxr-x   - hue    hue                 0 2016-12-08 21:48 /user/hue
drwxrwxr-x   - oozie  oozie               0 2016-12-08 21:49 /user/oozie
drwxrwxrwx   - hdfs   supergroup          0 2016-12-08 21:53 /user/orchard
drwxrwxrwx   - hdfs   supergroup          0 2016-12-08 21:53 /user/raffles


```

2) The output from the CM API call ../api/v14/hosts

```
{
  "items" : [ {
    "hostId" : "0a12e49e-9e3a-4297-b876-9290bf955be7",
    "ipAddress" : "172.31.1.151",
    "hostname" : "ip-172-31-1-151.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-1-155.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/0a12e49e-9e3a-4297-b876-9290bf955be7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "7f4e3912-71c1-41cf-aba2-97307d89bb25",
    "ipAddress" : "172.31.1.152",
    "hostname" : "ip-172-31-1-152.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-1-155.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/7f4e3912-71c1-41cf-aba2-97307d89bb25",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "932caf32-13db-4bf3-ad0b-026e451ebf7d",
    "ipAddress" : "172.31.1.153",
    "hostname" : "ip-172-31-1-153.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-1-155.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/932caf32-13db-4bf3-ad0b-026e451ebf7d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "89d6e92b-46e0-494a-82dc-10e9a14391db",
    "ipAddress" : "172.31.1.154",
    "hostname" : "ip-172-31-1-154.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-1-155.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/89d6e92b-46e0-494a-82dc-10e9a14391db",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-d02beb77",
    "ipAddress" : "172.31.1.155",
    "hostname" : "ip-172-31-1-155.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-1-155.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-d02beb77",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  } ]
}
```