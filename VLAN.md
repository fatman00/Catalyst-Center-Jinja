```
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
{% set create_vlan_str = create_vlan | string %}
vlan {{ create_vlan }}
 {% if vlan_db[create_vlan_str] is defined %}
 name {{ vlan_db[create_vlan_str] }}
 {% else %}
 name VLAN_{{ create_vlan }}
 {% endif %}
```
