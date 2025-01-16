# CLI Template
```
!
username cisco privilege 15 password C1sco12345
aaa new-model
!
!
aaa authentication login default local
aaa authentication login AAA_VTY group radius local
aaa authorization exec default local
aaa authorization exec AAA_VTY group radius local
{% for aaaserver in __aaanetworkserver %}
{% if 'RADIUS' in aaaserver.protocol %}
radius server RADIUS{{loop.index}}
 address ipv4 {{ aaaserver.ipAddress }} auth-port 1645 acct-port 1646
 key RADIUS
!
{% endif %}
{% endfor %}

interface GigabitEthernet0/0
 shutdown
!
no ip http server
ip http authentication aaa login-authentication AAA_VTY
ip http authentication aaa exec-authorization AAA_VTY
ip http secure-server

line vty 0 15
 exec-timeout 60 0
 authorization exec AAA_VTY
 logging synchronous
 login authentication AAA_VTY
 transport input ssh
 transport prefered none
```
