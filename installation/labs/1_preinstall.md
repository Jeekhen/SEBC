Current VMSwappiness is 30 

```
$ cat /proc/sys/vm/swappiness
>> 30

```

Change VMSwappiness to 1

```

$ sudo sysctl vm.swappiness=1
$ cat /proc/sys/vm/swappiness
>> 1
```

Showing Mounted drives 

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       30G  928M   30G   4% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
tmpfs           1.5G     0  1.5G   0% /run/user/1000

```

Disabling THP

```
sudo su
echo never > /sys/kernel/mm/transparent_hugepage/defrag
echo never > /sys/kernel/mm/transparent_hugepage/enabled

$  cat /sys/kernel/mm/transparent_hugepage/enabled
>>> always madvise [never]
```
 
Show the network attributes

```
$ip addr 

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:60:e4:e5:6d:3d brd ff:ff:ff:ff:ff:ff
    inet 172.31.1.80/20 brd 172.31.15.255 scope global dynamic eth0
       valid_lft 3336sec preferred_lft 3336sec
    inet6 fe80::60:e4ff:fee5:6d3d/64 scope link
       valid_lft forever preferred_lft forever
	   
```

Checking Forward and Reverse DNS
:q
```
$ getent hosts edge
172.31.14.158   ip-172-31-14-158.ap-southeast-1.compute.internal edge

```

Run a yum to install nslookup and then lookup

```
$ sudo yum install bind-utils
$ nslookup ip-172-31-14-158.ap-southeast-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-14-158.ap-southeast-1.compute.internal
Address: 172.31.14.158

```