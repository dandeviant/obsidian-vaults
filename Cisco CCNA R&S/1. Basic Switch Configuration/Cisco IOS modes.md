| Task | IOS Commands |
| --- | --- |
| Enter global configuration mode |  S1# configure terminal | 
| Enter interface configuration mode for the SVI | S1(config)# interface vlan 99<br>S1(config-vlan)# |
| Configure the management interface IPv4 address. | S1(config-if)# ip address 172.17.99.11 255.255.255.0 | 
| Configure the management interface IPv6 address | S1(config-if)# ipv6 address 2001:db8:acad:99::1/64 |
| Enable the management interface. | S1(config-if)# no shutdown |
| Return to the privileged EXEC mode. | S1(config-if)# end |
| Save the running config to the startup config. | S1# copy running-config startup-config |

---



