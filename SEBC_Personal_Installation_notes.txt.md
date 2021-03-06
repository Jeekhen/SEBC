```

Transparent Huge Page Compaction is enabled and can cause significant performance problems. Run "echo never > /sys/kernel/mm/transparent_hugepage/defrag" and "echo never > /sys/kernel/mm/transparent_hugepage/enabled" to disable this, then add the same command to an init script such as /etc/rc.local so it will be set upon system reboot. The following hosts are affected:


Cloudera recommends setting /proc/sys/vm/swappiness to a maximum of 10. Current setting is 30. Use the sysctl command to change this setting at run time and edit /etc/sysctl.conf for this setting to be saved after a reboot. You can continue with installation, but Cloudera Manager might report that your hosts are unhealthy because they are swapping. The following hosts are affected: 

    
-------------------- Pre Configuration Setup -------------------------   

sudo setenforce 0
sudo vi /etc/selinux/config

cat /proc/sys/vm/swappiness
sudo sysctl -w vm.swappiness=1

sudo su
echo never > /sys/kernel/mm/transparent_hugepage/defrag
echo never > /sys/kernel/mm/transparent_hugepage/enabled
sudo vi /etc/rc.local
systemctl stop tuned
systemctl disable tuned

--- if the above hugepage do not get turn off after reboot. Do the following

sudo vi /boot/grub/grub.conf 
-add : transparent_hugepage=never.... example below
"GRUB_CMDLINE_LINUX="rd.lvm.lv=rhel/root rd.lvm.lv=rhel/swap vconsole.font=latarcyrheb-sun16 vconsole.keymap=us transparent_hugepage=never"

Run:
grub2-mkconfig -o /boot/grub2/grub.cfg

reboot and check
cat /sys/kernel/mm/transparent_hugepage/enabled
-------------------

yum install bind-utils ntp nscd
yum install bind-utils
yum install ntp
yum install nscd

*** Need to configure your NTP server if you have a local NTP

systemctl start ntpd
systemctl enable ntpd
systemctl start nscd
systemctl enable nscd

getent hosts master
nslookup ip-172-31-14-159.ap-southeast-1.compute.internal
    
------------------------ MySQL Installation --------------------  

[mysql55-community]
name=MySQL 5.5 Community Server
baseurl=http://repo.mysql.com/yum/mysql-5.5-community/el/7/$basearch/
enabled=1
gpgcheck=0

(For Client / Slave nodes)
sudo yum install mysql
(For Server)
sudo yum install mysql-server mysql

tar zxvf mysql-connector-java-5.1.40.tar.gz
sudo mkdir -p /usr/share/java/
sudo cp mysql-connector-java-5.1.40/mysql-connector-java-5.1.40-bin.jar /usr/share/java/mysql-connector-java.jar

mkdir backup
cd backup
sudo mv /var/lib/mysql/ib_logfile0 .
sudo mv /var/lib/mysql/ib_logfile1 .

sudo systemctl start mysqld
sudo systemctl enable mysqld
sudo /usr/bin/mysql_secure_installation

* Only if you need replication, run the below steps. ---------------------------
mysql> CREATE USER 'repl'@'%.ap-southeast-1.compute.internal' IDENTIFIED BY 'slavepass';
mysql> GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%.ap-southeast-1.compute.internal';

mysql> FLUSH TABLES WITH READ LOCK;
mysql > SHOW MASTER STATUS;

mysql> CHANGE MASTER TO MASTER_HOST='ip-172-31-14-159.ap-southeast-1.compute.internal', MASTER_USER='repl', MASTER_PASSWORD='slavepass', MASTER_LOG_FILE='mysql_binary_log.000003', MASTER_LOG_POS=1627;

On Secondary Server:
mysql> START SLAVE;
--------------------------------------------------------------------------------------

create database amon DEFAULT CHARACTER SET utf8;
grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'amon_password';
create database rman DEFAULT CHARACTER SET utf8;
grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_password';
create database metastore DEFAULT CHARACTER SET utf8;
grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';
create database sentry DEFAULT CHARACTER SET utf8;
grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_password';
create database nav DEFAULT CHARACTER SET utf8;
grant all on nav.* TO 'nav'@'%' IDENTIFIED BY 'nav_password';
create database navms DEFAULT CHARACTER SET utf8;
grant all on navms.* TO 'navms'@'%' IDENTIFIED BY 'navms_password';

create database scm DEFAULT CHARACTER SET utf8;
grant all on scm.* TO 'scm'@'%' IDENTIFIED BY 'scm_password';

create database hue;
grant all on hue.* to 'hue'@'%' identified by 'secretpassword';

create database oozie;
grant all privileges on oozie.* to 'oozie'@'localhost' identified by 'oozie';
grant all privileges on oozie.* to 'oozie'@'%' identified by 'oozie';
    
	
	
----------------------------------- MySQL replication if needed ------------------------    
http://dev.mysql.com/doc/refman/5.7/en/replication-howto.html
If require replication

vi /etc/my.cnf
[mysqld]
log-bin=mysql-bin
server-id=1
* each server should have an unqiue server-id

mysql> CREATE USER 'repl'@'%.mydomain.com' IDENTIFIED BY 'slavepass';
mysql> GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%.mydomain.com';
mysql> FLUSH TABLES WITH READ LOCK;
mysql > SHOW MASTER STATUS;

you should see something like this
mysql > SHOW MASTER STATUS;
+------------------+----------+--------------+------------------+
| File             | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+------------------+----------+--------------+------------------+
| mysql-bin.000003 | 73       | test         | manual,mysql     |
+------------------+----------+--------------+------------------+


* On your secondary mysql server run this .....
mysql> CHANGE MASTER TO
    ->     MASTER_HOST='master_host_name',
    ->     MASTER_USER='repl',
    ->     MASTER_PASSWORD='slavepass',
    ->     MASTER_LOG_FILE='recorded_log_file_name',
    ->     MASTER_LOG_POS=recorded_log_position;

Slave nodes:
mysql> START SLAVE;

  
------------------------------Cloudera Manager installation -------------------    

cd /etc/yum.repos.d/
wget https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo

change baseurl to = https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.8.2/

sudo yum install oracle-j2sdk1.7
sudo yum install cloudera-manager-daemons cloudera-manager-server

/usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm scm_password
/usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm scm_password -h 192.9.202.196

 sudo service cloudera-scm-server start

http://ec2-54-254-178-8.ap-southeast-1.compute.amazonaws.com:7180/cmf/login

https://archive.cloudera.com/cdh5/parcels/5.8.2/

-------------------------------- HDFS Terasort and Teragen (Benmarking) ----------------------------    

time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Dmapred.map.tasks.speculative.execution=false -Ddfs.block.size=32M 100000000 terasort-input 

time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort terasort-input /user/jeekhen

------------------------------------ CDH Upgrade --------------------------------    

wget https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5/
sudo yum upgrade cloudera-manager-server cloudera-manager-daemons cloudera-manager-agent

--------------------------------------- Keboros -----------------------------------    

[root@ip-172-31-14-159 ~]# id jeekhen
uid=1002(jeekhen) gid=1002(jeekhen) groups=1002(jeekhen)

sudo adduser jeekhen
sudo passwd jeekhen

sudo groupadd group_name
sudo groupadd -g GID

sudo usermod -u 1002 jeekhen
sudo groupmod -g 1002 jeekhen

http://blog.puneethabm.in/configure-hadoop-security-with-cloudera-manager-using-kerberos/

sudo yum install krb5-server krb5-libs krb5-auth-dialog
sudo yum install krb5-workstation krb5-libs krb5-auth-dialog

AP-SOUTHEAST-1.COMPUTE.INTERNAL
ap-southeast-1.compute.internal

edit: 
/etc/krb5.conf - /var/kerberos/krb5kdc/kdc.conf - /var/kerberos/krb5kdc/kadm5.acl
kdc file parameters;
  max_life = 1d
  max_renewable_life = 7d
  
/usr/sbin/kdb5_util create -s

/usr/sbin/kadmin.local -q "addprinc jeekhen/admin"
/sbin/service krb5kdc start
/sbin/service kadmin start

Kerberos Client:
addprinc -randkey host/server.example.com
In kadmin:
ktadd -k /etc/krb5.keytab host/server.example.com



###################### TLS ####################################
export JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
export PATH=$JAVA_HOME/bin:$PATH

Run as (Root User)

sudo mkdir /opt/cloudera/security
sudo mkdir /opt/cloudera/security/CAcerts

http://www.cloudera.com/documentation/enterprise/latest/topics/sg_self_signed_tls.html

mkdir -p /opt/cloudera/security/x509/ /opt/cloudera/security/jks/
chown -R cloudera-scm:cloudera-scm /opt/cloudera/security/jks
cd /opt/cloudera/security/jks

keytool -genkeypair -alias cmhost -keyalg RSA -keystore \
/opt/cloudera/security/jks/cmhost-keystore.jks -keysize 2048 -dname \
"CN=http://ec2-54-179-163-208.ap-southeast-1.compute.amazonaws.com,OU=Security,O=Example,L=Denver,ST=Colorado,C=US" \
-storepass password -keypass password

sudo cp $JAVA_HOME/jre/lib/security/cacerts $JAVA_HOME/jre/lib/security/jssecacerts

keytool -export -alias cmhost -keystore /opt/cloudera/security/jks/cmhost-keystore.jks -rfc -file selfsigned.cer

cp selfsigned.cer /opt/cloudera/security/x509/cmhost.pem

keytool -import -alias cmhost -file /opt/cloudera/security/jks/selfsigned.cer \
-keystore $JAVA_HOME/jre/lib/security/jssecacerts -storepass changeit

Go to each client 
sudo vi /etc/cloudera-scm-agent/config.ini
TLS = 1
sudo mv config.ini  /etc/cloudera-scm-agent/config.ini

sudo service cloudera-scm-server restart 
sudo service cloudera-scm-agent restart











------------------------------------ Misc notes --------------------------    

keytool -exportcert -keystore /opt/cloudera/security/jks/cmhost-keystore.jks -alias cmhost -storepass password -file node1.cer

keytool -importcert -keystore custom.truststore -alias cmhost \
-storepass password -file node1.cer -noprompt

sudo cp $JAVA_HOME/jre/lib/security/cacerts $JAVA_HOME/jre/lib/security/jssecacerts

keytool -export -alias cmhost -keystore custom.truststore -rfc -file selfsigned.cer

cp selfsigned.cer /opt/cloudera/security/x509/cmhost.pem

keytool -import -alias cmhost -file /opt/cloudera/security/jks/selfsigned.cer \
-keystore $JAVA_HOME/jre/lib/security/jssecacerts -storepass changeit

Go to each client 
sudo vi /etc/cloudera-scm-agent/config.ini
TLS = 1
sudo mv config.ini  /etc/cloudera-scm-agent/config.ini



```





















