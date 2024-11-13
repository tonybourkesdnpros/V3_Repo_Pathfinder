# ISP-1

## Table of Contents

- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
  - [Loopback Interfaces](#loopback-interfaces)
- [Routing](#routing)
  - [IP Routing](#ip-routing)
  - [Router BGP](#router-bgp)
- [Filters](#filters)
  - [Prefix-lists](#prefix-lists)

## Spanning Tree

### Spanning Tree Summary

STP mode: **none**

### Spanning Tree Device Configuration

```eos
!
spanning-tree mode none
```

## Interfaces

### Ethernet Interfaces

#### Ethernet Interfaces Summary

##### L2

| Interface | Description | Mode | VLANs | Native VLAN | Trunk Group | Channel-Group |
| --------- | ----------- | ---- | ----- | ----------- | ----------- | ------------- |

*Inherited from Port-Channel Interface

##### IPv4

| Interface | Description | Type | Channel Group | IP Address | VRF |  MTU | Shutdown | ACL In | ACL Out |
| --------- | ----------- | -----| ------------- | ---------- | ----| ---- | -------- | ------ | ------- |
| Ethernet1 | - | routed | - | 11.11.51.1/24 | default | 1500 | False | - | - |
| Ethernet2 | - | routed | - | 11.11.52.1/24 | default | 1500 | False | - | - |
| Ethernet3 | - | routed | - | 11.11.1.1/24 | default | 1500 | False | - | - |
| Ethernet4 | - | routed | - | 11.11.2.1/24 | default | 1500 | False | - | - |
| Ethernet5 | - | routed | - | 11.11.10.1/24 | default | 1500 | False | - | - |
| Ethernet7 | - | routed | - | 11.11.12.1/24 | default | 1500 | False | - | - |
| Ethernet8 | - | routed | - | 11.11.13.1/24 | default | 1500 | False | - | - |
| Ethernet9 | - | routed | - | 11.11.14.1/24 | default | 1500 | False | - | - |
| Ethernet10 | - | routed | - | 3.3.1.2/24 | default | 1500 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.51.1/24
!
interface Ethernet2
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.52.1/24
!
interface Ethernet3
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.1.1/24
!
interface Ethernet4
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.2.1/24
!
interface Ethernet5
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.10.1/24
!
interface Ethernet6
   shutdown
   mtu 1500
   no switchport
!
interface Ethernet7
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.12.1/24
!
interface Ethernet8
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.13.1/24
!
interface Ethernet9
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.14.1/24
!
interface Ethernet10
   no shutdown
   mtu 1500
   no switchport
   ip address 3.3.1.2/24
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback10 | ISP_lo10 | default | 192.168.0.16/32 |

##### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback10 | ISP_lo10 | default | - |

#### Loopback Interfaces Device Configuration

```eos
!
interface Loopback10
   description ISP_lo10
   no shutdown
   ip address 192.168.0.16/32
```

## Routing

### IP Routing

#### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | True |

#### IP Routing Device Configuration

```eos
!
ip routing
```

### Router BGP

ASN Notation: asplain

#### Router BGP Summary

| BGP AS | Router ID |
| ------ | --------- |
| 65103 | 192.168.0.16 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive | TTL Max Hops |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- | ------------ |
| 3.3.1.1 | 65002 | default | - | - | - | - | - | - | - | - | - |
| 11.11.10.2 | 65000 | default | - | - | - | - | - | - | - | - | - |
| 11.11.12.2 | 65000 | default | - | - | - | - | - | - | - | - | - |
| 11.11.13.2 | 65000 | default | - | - | - | - | - | - | - | - | - |
| 11.11.14.2 | 65000 | default | - | - | - | - | - | - | - | - | - |

#### Router BGP Device Configuration

```eos
!
router bgp 65103
   router-id 192.168.0.16
   neighbor 3.3.1.1 remote-as 65002
   neighbor 3.3.1.1 description ISP-3
   neighbor 11.11.10.2 remote-as 65000
   neighbor 11.11.10.2 description Edge10
   neighbor 11.11.10.2 default-originate
   neighbor 11.11.12.2 remote-as 65000
   neighbor 11.11.12.2 description Edge12
   neighbor 11.11.12.2 default-originate
   neighbor 11.11.13.2 remote-as 65000
   neighbor 11.11.13.2 description Edge13
   neighbor 11.11.13.2 default-originate
   neighbor 11.11.14.2 remote-as 65000
   neighbor 11.11.14.2 description Edge14
   neighbor 11.11.14.2 default-originate
   !
   address-family ipv4
      neighbor 11.11.10.2 prefix-list INTERNET in
      neighbor 11.11.10.2 activate
      neighbor 11.11.12.2 prefix-list INTERNET in
      neighbor 11.11.12.2 activate
      neighbor 11.11.13.2 prefix-list INTERNET in
      neighbor 11.11.13.2 activate
      neighbor 11.11.14.2 prefix-list INTERNET in
      neighbor 11.11.14.2 activate
      redistribute connected
```

## Filters

### Prefix-lists

#### Prefix-lists Summary

##### INTERNET

| Sequence | Action |
| -------- | ------ |
| 10 | permit 11.11.0.0/16 eq 24 |

#### Prefix-lists Device Configuration

```eos
!
ip prefix-list INTERNET
   seq 10 permit 11.11.0.0/16 eq 24
```
