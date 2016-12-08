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
```