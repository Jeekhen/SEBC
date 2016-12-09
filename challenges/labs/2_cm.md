1) List the command and output of ls /etc/yum.repos.d in challenges/labs/2_cm.md

```
[root@ip-172-31-1-155 ~]# ls /etc/yum.repos.d
cloudera-manager.repo  redhat.repo                     redhat-rhui.repo
mysql-community.repo   redhat-rhui-client-config.repo  rhui-load-balancers.conf
```

2)Use the scm_prepare_database.sh script to write your db.properties file

```
/usr/share/cmf/schema/scm_prepare_database.sh -hec2-54-251-190-59.ap-southeast-1.compute.amazonaws.com mysql scm scm scm_password 
```