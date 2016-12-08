```

1) What is ubertask optimization?
Ans: Uber Task are running mapper and reducer job within the application master. Thus ubertask optimization would be the process to tune the parameters to allow to uber task to run at optimal.

2) Where in CM is the Kerberos Security Realm value displayed?
Ans: It is under the Administration tab in the security sub tab.

3) Which CDH service(s) host a property for enabling Kerberos authentication?
Ans: 
hdfs	NameNode, DataNodes, and Secondary Node
mapred	JobTracker and TaskTrackers (MR1) and Job History Server (YARN)
yarn	ResourceManager and NodeManagers (YARN)
oozie	Oozie Server
hue		Hue Server, Beeswax Server, Authorization Manager, and Job Designer

4) How do you upgrade the CM agents?
Ans: we can upgrade agent manaually through "sudo yum upgrade ..."

5) Give the tsquery statement used to chart Hue's CPU utilization?
Ans: select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=Hue

6) Name all the roles that make up the Hive service
Ans: Hive Metastore, HiveServer2 and Hive Gateway

7) What steps must be completed before integrating Cloudera Manager with Kerberos?
Ans: Setup KDC, configure renewable ticket, install openldap client library and create the necessary user in CM.