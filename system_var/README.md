# System Variables
Within the Catalyst Center some variable for the sites are configured under the Design menu.

The variables defined here can be access in system variables in Jinja Templates
![System Variables](SYSVAR2.png)

## CLI Template
```
!
{% for nameserver in __dnsserver %}
ip name-server {{nameserver.primaryIpAddress}} {{nameserver.secondaryIpAddress}}
ip domain name {{nameserver.domainName}}
{% endfor %}
!
interface GigabitEthernet0/0
 shutdown
!
```
