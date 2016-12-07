Command that was ran for teragen

```
$ time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Dmapred.map.tasks.speculative.execution=false -Ddfs.block.size=32M 100000000 terasort-input 

```

Result of Teragen

```
16/12/07 03:52:36 INFO mapreduce.Job: Job job_1481100393580_0001 completed successfully
16/12/07 03:52:36 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=488800
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=529027
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=529027
                Total vcore-seconds taken by all map tasks=529027
                Total megabyte-seconds taken by all map tasks=541723648
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1132
                CPU time spent (ms)=156900
                Physical memory (bytes) snapshot=704024576
                Virtual memory (bytes) snapshot=6311333888
                Total committed heap usage (bytes)=904921088
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10000000000

real    2m30.974s
user    0m6.010s
sys     0m0.280s
```

Command that was ran for Terasort

```
$ time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort terasort-input /user/jeekhen
```

Result of Terasort

```
16/12/07 04:10:25 INFO mapreduce.Job: Job job_1481100393580_0002 completed successfully
16/12/07 04:10:25 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=4445510915
                FILE: Number of bytes written=8826418641
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10000049800
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=924
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=300
                Launched reduce tasks=8
                Data-local map tasks=300
                Total time spent by all maps in occupied slots (ms)=2052735
                Total time spent by all reduces in occupied slots (ms)=876425
                Total time spent by all map tasks (ms)=2052735
                Total time spent by all reduce tasks (ms)=876425
                Total vcore-seconds taken by all map tasks=2052735
                Total vcore-seconds taken by all reduce tasks=876425
                Total megabyte-seconds taken by all map tasks=2102000640
                Total megabyte-seconds taken by all reduce tasks=897459200
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Map output bytes=10200000000
                Map output materialized bytes=4342807264
                Input split bytes=49800
                Combine input records=0
                Combine output records=0
                Reduce input groups=100000000
                Reduce shuffle bytes=4342807264
                Reduce input records=100000000
                Reduce output records=100000000
                Spilled Records=200000000
                Shuffled Maps =2400
                Failed Shuffles=0
                Merged Map outputs=2400
                GC time elapsed (ms)=26268
                CPU time spent (ms)=1305930
                Physical memory (bytes) snapshot=150101827584
                Virtual memory (bytes) snapshot=487244709888
                Total committed heap usage (bytes)=173374177280
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10000000000
        File Output Format Counters
                Bytes Written=10000000000
16/12/07 04:10:25 INFO terasort.TeraSort: done

real    5m57.532s
user    0m9.032s
sys     0m0.347s

```