1)The full teragen command
```
time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=8 -Dmapred.map.tasks.speculative.execution=false -Ddfs.block.size=32M 51200000 tgen512m
```

2)The output of the time command
```
real    1m13.168s
user    0m5.731s
sys     0m0.271s
```

3)The command and output of hdfs dfs -ls /user/raffles/tgen512m
```
[raffles@ip-172-31-1-155 ec2-user]$ hdfs dfs -ls /user/raffles/tgen512m
Found 9 items
-rw-r--r--   3 raffles supergroup          0 2016-12-08 22:14 /user/raffles/tgen512m/_SUCCESS
-rw-r--r--   3 raffles supergroup  640000000 2016-12-08 22:14 /user/raffles/tgen512m/part-m-00000
-rw-r--r--   3 raffles supergroup  640000000 2016-12-08 22:14 /user/raffles/tgen512m/part-m-00001
-rw-r--r--   3 raffles supergroup  640000000 2016-12-08 22:14 /user/raffles/tgen512m/part-m-00002
-rw-r--r--   3 raffles supergroup  640000000 2016-12-08 22:14 /user/raffles/tgen512m/part-m-00003
-rw-r--r--   3 raffles supergroup  640000000 2016-12-08 22:14 /user/raffles/tgen512m/part-m-00004
-rw-r--r--   3 raffles supergroup  640000000 2016-12-08 22:14 /user/raffles/tgen512m/part-m-00005
-rw-r--r--   3 raffles supergroup  640000000 2016-12-08 22:14 /user/raffles/tgen512m/part-m-00006
-rw-r--r--   3 raffles supergroup  640000000 2016-12-08 22:14 /user/raffles/tgen512m/part-m-00007

```

4)Show how many blocks are linked to this directory
```
[raffles@ip-172-31-1-155 ec2-user]$ hdfs fsck /user/raffles/tgen512m -blocks
Connecting to namenode via http://ip-172-31-1-151.ap-southeast-1.compute.internal:50070
FSCK started by raffles (auth:SIMPLE) from /172.31.1.155 for path /user/raffles/tgen512m at Thu Dec 08 22:18:13 EST 2016
.........Status: HEALTHY
 Total size:    5120000000 B
 Total dirs:    1
 Total files:   9
 Total symlinks:                0
 Total blocks (validated):      160 (avg. block size 32000000 B)
 Minimally replicated blocks:   160 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Thu Dec 08 22:18:13 EST 2016 in 9 milliseconds


The filesystem under path '/user/raffles/tgen512m' is HEALTHY
```
