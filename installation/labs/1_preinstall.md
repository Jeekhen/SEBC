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
[ec2-user@ip-172-31-1-80 ~]$ df -h
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
$ vi /etc/sysconfig/grub
```

Append line 'transparent_hugepage=never'  
Reboot system

Check if parameter is updated

```
$ cat /proc/cmdline
>>> BOOT_IMAGE=/boot/vmlinuz-3.10.0-327.el7.x86_64 root=UUID=379de64d-ea11-4f5b-ae6a-0aa50ff7b24d ro console=ttyS0,115200n8 console=tty0 net.ifnames=0 crashkernel=auto transparent_hugepage=never

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

```
$ getent hosts edge
172.31.1.80     edge.cloudera edge
```

Run a yum to install nslookup and then lookup

```
$ sudo yum install bind-util
$ nslookup ip-172-31-1-80.ap-southeast-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-1-80.ap-southeast-1.compute.internal
Address: 172.31.1.80

```