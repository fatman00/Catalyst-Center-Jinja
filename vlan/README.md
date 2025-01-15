# VLANs
Creating and managing VLANs is easy using the built in variable editor and the variable system.

In this example I have created a multi-select variable where we can select the VLANs we need to create on the switch and provision the template.
## CLI Template
```
{% for vlan in vlan_db %}
{% set vlansplit = vlan.split(';') %}
vlan {{ vlansplit[0] }}
 name {{ vlansplit[1] }}
!
{% endfor %}
```
## Variable definitions
![Variables configuration](VLAN_DB_VARs.png)

## Simulation
Running the simulation
![Simulation](VLAN_DB_SIM.png)

**Simulation output**
```
vlan 10
 name admin
!
vlan 20
 name prod
!
vlan 50
 name mgmt
!
```
