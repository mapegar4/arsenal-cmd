# huawei

% network, switch, huawei

#platform/huawei #target/switch #cat/NETWORK

## Enter System View (Configuration Mode)
```
system-view
```

## Display Current Configuration
```
display current-configuration
```

## Display Interfaces Information
```
display interfaces
```

## Display All VLANs
```
display vlan all
```

## Display Version Information
```
display version
```

## Display Interface Descriptions
```
display interface description
```

## Change Device Name
```
sysname <name>
```

## Enter Interface View (Ethernet)
```
interface ethernet 0/0/1
```

## Enter VLAN Interface View
```
interface vlanif <vlan-id>
```

## Configure IP Address on VLAN Interface
```
ip address <ip> <mask> 
```

## Add Static Route
```
ip route-static <ip> <mask> <gateway>
```

## Enable Port (Undo Shutdown)
```
undo shutdown
```

## Disable Port (Shutdown)
```
shutdown
```

## Exit Current View
```
quit
```

## Save Configuration (User View)
```
save
```

## Display Interface Brief (Status Summary)
```
display interface brief
```

## Display MAC Address Table
```
display mac-address
```

## Assign Port to VLAN (Access Mode)
```
interface ethernet 0/0/1
port link-type access
port default vlan <vlan-id>
```

## Configure Trunk Port
```
interface ethernet 0/0/24
port link-type trunk
port trunk allow-pass vlan-list
```

## Disable Telnet (Security Best Practice)
```
undo telnet server enable
```

## Enable SSH
```
stelnet server enable
```

## Configure VTY Lines for SSH Only
```
user-interface vty 0 4
authentication-mode aaa
protocol inbound ssh
```

## Create Local Admin User for SSH Access
```
aaa
local-user admin password irreversible-cipher <password>
local-user admin privilege level 15
local-user admin service-type ssh
```

## Display System Log Buffer
```
display logbuffer
```

## Display CPU Usage
```
display cpu-usage
```

## Display Memory Usage
```
display memory-usage
```
