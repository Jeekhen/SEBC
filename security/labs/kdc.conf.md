```
[libdefaults]
default_realm = AP-SOUTHEAST-1.COMPUTE.INTERNAL
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 24h
renew_lifetime = 7d
forwardable = true
default_tgs_enctypes = arcfour-hmac
default_tkt_enctypes = arcfour-hmac
permitted_enctypes = arcfour-hmac
udp_preference_limit = 1
kdc_timeout = 3000
[realms]
AP-SOUTHEAST-1.COMPUTE.INTERNAL = {
kdc = ip-172-31-14-159.ap-southeast-1.compute.internal
admin_server = ip-172-31-14-159.ap-southeast-1.compute.internal
}
[root@ip-172-31-14-159 ec2-user]# ^C
[root@ip-172-31-14-159 ec2-user]# sudo cat /var/kerberos/krb5kdc/kdc.conf
[kdcdefaults]
 kdc_ports = 88
 kdc_tcp_ports = 88

[realms]
 AP-SOUTHEAST-1.COMPUTE.INTERNAL = {
  #master_key_type = aes256-cts
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  dict_file = /usr/share/dict/words
  admin_keytab = /var/kerberos/krb5kdc/kadm5.keytab
  supported_enctypes = aes256-cts:normal aes128-cts:normal des3-hmac-sha1:normal arcfour-hmac:normal camellia256-cts:normal camellia128-cts:normal des-hmac-sha1:normal des-cbc-md5:normal des-cbc-crc:normal
  max_life = 1d
  max_renewable_life = 7d
 }
```