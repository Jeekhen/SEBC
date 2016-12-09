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