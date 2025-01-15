# Interface configuration
To help with interface configuration we will use the built ind bindings.

Let us assume we have different interface types we need to configure:
- Uplinks
- Downlinks
- User ports
- Printer ports
- Access Point Ports

## Uplink
The default configuration on an uplink port will look something like this:
```
interface GigabitEthernet1/0/1
 description UPLINK -> DKDEM01SW01
 switchport
 switchport encapsulation dot1q
 switchport mode trunk
 switchport nonegotiate
```

## Downlink
The default configuration on an downlink port will look something like this:
```
interface GigabitEthernet1/0/2
 description DOWNLINK -> DKDEM01SW10
 switchport
 switchport encapsulation dot1q
 switchport mode trunk
 switchport nonegotiate
```

## User port
The default configuration on an user port will look something like this:
```
interface GigabitEthernet1/0/2
 description < USERPORT >
 switchport
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast
```

## Print port
The default configuration on a printer port will look something like this:
```
interface GigabitEthernet1/0/2
 description < PRINTER >
 switchport
 switchport mode access
 switchport access vlan 110
 spanning-tree portfast
 speed 100
 port-security
 
```
