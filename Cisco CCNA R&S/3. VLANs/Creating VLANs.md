Show VLAN created

> Switch# show vlan brief

### VLAN Creation Commands

| **Task** | **IOS Command** |
| --- | --- |
| Enter global configuration mode. | Switch# **configure terminal** |
| Create a VLAN with a valid ID number. | Switch(config)# **vlan** _vlan-id_ |
| Specify a unique name to identify the VLAN. | Switch(config-vlan)# **name** _vlan-name_ |
| Return to the privileged EXEC mode. | Switch(config-vlan)# **end** | 

Examples

>```text
>S1# configure terminal 
>S1(config)# vlan 20 
>S1(config-vlan)# name student
>S1(config-vlan)# end





