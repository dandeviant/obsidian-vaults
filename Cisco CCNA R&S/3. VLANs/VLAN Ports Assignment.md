| **Task** | **IOS Command** | 
| --- | --- |
| Enter global configuration mode. | Switch# **configure terminal**|
| Enter interface configuration mode. | Switch(config)# **interface** _interface-id_ | 
| Set the port to access mode. | Switch(config-if)# **switchport mode access** | 
| Assign the port to a VLAN. | Switch(config-if)# **switchport access vlan** _vlan -id_ |
| Return to the privileged EXEC mode. | Switch(config-if)# **end** | 

Example
>```S1# configure terminal
>S1(config)# interface fa0/6
>S1(config-if)# switchport mode access
>S1(config-if)# switchport access vlan 20
>S1(config-if)# end