Provide my /etc/hosts
```
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6

172.31.1.151 ip-172-31-1-151.ap-southeast-1.compute.internal master
172.31.1.152 ip-172-31-1-152.ap-southeast-1.compute.internal data1
172.31.1.153 ip-172-31-1-153.ap-southeast-1.compute.internal data2
172.31.1.154 ip-172-31-1-154.ap-southeast-1.compute.internal data3
172.31.1.155 ip-172-31-1-155.ap-southeast-1.compute.internal edge
```

1) The hostname of your MySQL node: hostname is ip-172-31-1-151.ap-southeast-1.compute.internal or master
```
[ec2-user@ip-172-31-1-151 ~]$ mysql -u root -p -hlocalhost
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 13
Server version: 5.5.53 MySQL Community Server (GPL)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>

```

2) The command and output for mysql --version
```
[ec2-user@ip-172-31-1-151 ~]$ mysql --version
mysql  Ver 14.14 Distrib 5.5.53, for Linux (x86_64) using readline 5.1

```

3) The command and output for listing MySQL databases
```
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| hue                |
| metastore          |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
12 rows in set (0.00 sec)
```


