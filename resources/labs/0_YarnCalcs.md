```
Did not adjust much of the default values except included for 1 GB of memory and 1 vcores to impalad, hbase and solr.

As optimal performace can only be tuned depending on the customer specific workload and on the ground testing. Default values for resource should be kept until more detail from the customers are give. Different type of job such as real-time streaming, ETL or even running machine learning batch jobs (Mahout, MLlib, etc) may require the Java heap size to be increased accordingly.

For workload factor, by increase the value, it has automatically increased the number of mapper and reducer that can be call by the client. This indicates that the high the workload factor mean that customer may require heavy computation job that require an increase number of map or reduce to run parallelly.

```