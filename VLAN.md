{% set vlan_db = {
  "1": "DO NOT USE",
  "10": "Management VLAN",
  "15": "Printer VLAN",
  "20": "Voice VLAN",
  "123": "Guest VLAN",
  "777": "POS VLAN",
  "999": "Blackhole VLAN"
  } 
%}

{% for vlan in vlan_db %}
vlan {{ vlan }}
 name {{vlan_db[vlan]}}
!
{% endfor %}
