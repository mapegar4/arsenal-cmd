# HuaweiGPON

% network, gpon, huawei

#platform/huawei #target/olt #cat/NETWORK

## Display Version
```
display version
```

## Display Interfaces
```
display interface
```

## Display Saved Configuration
```
display saved-configuration
```

## Display IP/Routing
```
display ip interfaces
display ip routing-table
```

## Add Default Route
```
ip route-static <ip> <mask> <gateway>
```

## Add SSH User
```
ssh user "test" authentication-type password
```

## Add Board (Example: Slot 5 GPON 16 port)
```
board add 0/5 H901GPHF
```

## Configure VLANs (Smart Mode)
```
vlan <vlan-id> smart
```

## Assign VLANs to Uplink Port (Example:port vlan 100 0/8 port 0)
```
port vlan <vlan-id> <slot> <port>
```

## Define DBA Profiles
```
dba-profile add profile-id <profile-id> profile-name "MGNT" type1 fix 1024
dba-profile add profile-id <profile-id> profile-name "INTERNET" type3 assure 10000 max 200000
```

## Define Traffic Tables
```
traffic table ip index 100 name "MGNT" cir 512 cbs 329680 pir 1024 pbs 329680 color-mode color-blind priority 7 priority-policy local-setting
traffic table ip index 101 name "INTERNET_100_DOWN" cir 10000 cbs 329680 pir 100000 pbs 329680 priority 0 priority-policy local-Setting
traffic table ip index 102 name "INTERNET_20_UP" cir 4096 cbs 329680 pir 20000 pbs 329680 priority 0 priority-policy local-Setting
```

## Configure ONT Line Profile
```
ont-lineprofile gpon profile-id 20 profile-name "FTTH-100"
tcont 1 dba-profile-id 100
tcont 2 dba-profile-id 102
gem add 1 eth tcont 1
gem add 2 eth tcont 2
gem mapping 1 1 vlan 100
gem mapping 2 2 vlan 200
commit
```

## Configure ONT Service Profile
```
ont-srvprofile gpon profile-id 20 profile-name "FTTH-100" ont-port pots adaptive eth adaptive commit
```

## Enable ONT Auto Find
```
interface gpon 0/5
port 0 ont-auto-find enable
```

## Add ONT manually
```
interface gpon 0/5
ont add 0 1 sn-auth "4857544352E92103" omci ont-lineprofile-id 20 ont-srvprofile-id 20 desc "CUSTOMER-1"
```

## Define Service Ports (VLAN Mapping)
```
service-port 1001 vlan 100 gpon 0/5/0 ont 1 gemport 1 multi-service user-vlan 100 tag-transform translate inbound traffic-table index 10 outbound traffic-table index 10
```

## Display ONT Info
```
display ont info 0 5 0 all
display ont info summary 0/5
display ont autofind all
```

## Display Board Info
```
display board 0
display board 0/5
```

## Display Profiles
```
display dba-profile all
display ont-lineprofile gpon all
display ont-srvprofile gpon all
```

## Remove ONT (Undo Service Port & Delete)
```
undo service-port 1001
interface gpon 0/5
ont delete 0 0
```
