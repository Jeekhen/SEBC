```
1) Instance_ID
i-cc2beb6b (Cloudera Master)
i-cd2beb6a (Cloudera Data1)
i-d02beb77 (Cloudera Edge)
i-d22beb75 (Cloudera Data2)
i-d32beb74 (Cloudera Data3)

AMI that i a using Red Hat Enterprise Linux (RHEL) 7.2 (HVM)
AMI ID = RHEL-7.2_HVM_GA-20151112-x86_64-1-Hourly2-GP2 (ami-3f03c55c)

```

2) list volume space

```
[ec2-user@ip-172-31-1-151 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       80G  928M   80G   2% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
tmpfs           1.5G     0  1.5G   0% /run/user/1000
```

3) List the command and output for yum repolist enabled

```

[ec2-user@ip-172-31-1-151 ~]$ yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Could not contact CDS load balancer rhui2-cds01.ap-southeast-1.aws.ce.redhat.com, trying others.


Could not contact any CDS load balancers: rhui2-cds01.ap-southeast-1.aws.ce.redhat.com, rhui2-cds02.ap-southeast-1.aws.ce.redhat.com.
[ec2-user@ip-172-31-1-151 ~]$ sudo yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
rhui-REGION-client-config-server-7                       | 2.9 kB     00:00
rhui-REGION-rhel-server-releases                         | 3.5 kB     00:00
rhui-REGION-rhel-server-rh-common                        | 3.8 kB     00:00
(1/7): rhui-REGION-client-config-server-7/x86_64/primary_d | 5.4 kB   00:00
(2/7): rhui-REGION-rhel-server-releases/7Server/x86_64/gro | 701 kB   00:00
(3/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/gr |  104 B   00:00
(4/7): rhui-REGION-rhel-server-releases/7Server/x86_64/upd | 1.8 MB   00:00
(5/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/pr | 110 kB   00:00
(6/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/up |  29 kB   00:00
(7/7): rhui-REGION-rhel-server-releases/7Server/x86_64/pri |  32 MB   00:00
repo id                                          repo name                status
rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastru      6
rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux 13,540
rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux    209
repolist: 13,755

```

List the /etc/passwd entries for raffles and orchard in your setup file

```
[ec2-user@ip-172-31-1-151 ~]$ sudo cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
operator:x:11:0:operator:/root:/sbin/nologin
games:x:12:100:games:/usr/games:/sbin/nologin
ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin
nobody:x:99:99:Nobody:/:/sbin/nologin
avahi-autoipd:x:170:170:Avahi IPv4LL Stack:/var/lib/avahi-autoipd:/sbin/nologin
systemd-bus-proxy:x:999:997:systemd Bus Proxy:/:/sbin/nologin
systemd-network:x:998:996:systemd Network Management:/:/sbin/nologin
dbus:x:81:81:System message bus:/:/sbin/nologin
polkitd:x:997:995:User for polkitd:/:/sbin/nologin
tss:x:59:59:Account used by the trousers package to sandbox the tcsd daemon:/dev/null:/sbin/nologin
postfix:x:89:89::/var/spool/postfix:/sbin/nologin
chrony:x:996:993::/var/lib/chrony:/sbin/nologin
sshd:x:74:74:Privilege-separated SSH:/var/empty/sshd:/sbin/nologin
ec2-user:x:1000:1000:Cloud User:/home/ec2-user:/bin/bash
raffles:x:2700:1001::/home/raffles:/bin/bash
orchard:x:2800:2701::/home/orchard:/bin/bash
```

List the /etc/group entries for shops and walks in your setup file

```
[ec2-user@ip-172-31-1-151 ~]$ sudo cat /etc/group
root:x:0:
bin:x:1:
daemon:x:2:
sys:x:3:
adm:x:4:ec2-user
tty:x:5:
disk:x:6:
lp:x:7:
mem:x:8:
kmem:x:9:
wheel:x:10:ec2-user
cdrom:x:11:
mail:x:12:postfix
man:x:15:
dialout:x:18:
floppy:x:19:
games:x:20:
tape:x:30:
video:x:39:
ftp:x:50:
lock:x:54:
audio:x:63:
nobody:x:99:
users:x:100:
avahi-autoipd:x:170:
utmp:x:22:
utempter:x:35:
ssh_keys:x:999:
input:x:998:
systemd-journal:x:190:ec2-user
systemd-bus-proxy:x:997:
systemd-network:x:996:
dbus:x:81:
polkitd:x:995:
tss:x:59:
dip:x:40:
cgred:x:994:
postdrop:x:90:
postfix:x:89:
chrony:x:993:
sshd:x:74:
ec2-user:x:1000:
raffles:x:1001:
orchard:x:2701:
shops:x:2702:orchard
walks:x:2703:raffles
```