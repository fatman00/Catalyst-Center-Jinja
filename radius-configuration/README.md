# CLI Template
```
!
{% for nameserver in __dnsserver %}
ip name-server {{nameserver.primaryIpAddress}} {{nameserver.secondaryIpAddress}}
ip domain name {{nameserver.domainName}}
{% endfor %}
!
{% for timeserver in __ntpserver %}
ntp server {{timeserver}}
{% endfor %}

{% for aaaserver in __aaanetworkserver %}
{% if 'RADIUS' in aaaserver.protocol %}
radius server RADIUS01
 address ipv4 {{ aaaserver.ipAddress }} auth-port 1645 acct-port 1646
 key RADIUS
!
{% endif %}
{% endfor %}

interface GigabitEthernet0/0
 shutdown
!
```
