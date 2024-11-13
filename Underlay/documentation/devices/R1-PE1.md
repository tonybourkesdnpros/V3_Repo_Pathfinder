# R1-PE1

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
| Ethernet1 | - | routed | - | 172.16.51.1/24 | default | 1500 | False | - | - |
| Ethernet2 | - | routed | - | 172.16.52.1/24 | default | 1500 | False | - | - |
| Ethernet3 | - | routed | - | 172.16.1.1/24 | default | 1500 | False | - | - |
| Ethernet4 | - | routed | - | 172.16.2.1/24 | default | 1500 | False | - | - |
| Ethernet5 | - | routed | - | 172.16.10.1/24 | default | 1500 | False | - | - |
| Ethernet7 | - | routed | - | 172.16.12.1/24 | default | 1500 | False | - | - |
| Ethernet8 | - | routed | - | 172.16.13.1/24 | default | 1500 | False | - | - |
| Ethernet9 | - | routed | - | 172.16.14.1/24 | default | 1500 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   no shutdown
   mtu 1500
   no switchport
   ip address 172.16.51.1/24
!
interface Ethernet2
   no shutdown
   mtu 1500
   no switchport
   ip address 172.16.52.1/24
!
interface Ethernet3
   no shutdown
   mtu 1500
   no switchport
   ip address 172.16.1.1/24
!
interface Ethernet4
   no shutdown
   mtu 1500
   no switchport
   ip address 172.16.2.1/24
!
interface Ethernet5
   no shutdown
   mtu 1500
   no switchport
   ip address 172.16.10.1/24
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
   ip address 172.16.12.1/24
!
interface Ethernet8
   no shutdown
   mtu 1500
   no switchport
   ip address 172.16.13.1/24
!
interface Ethernet9
   no shutdown
   mtu 1500
   no switchport
   ip address 172.16.14.1/24
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback10 | R2-PE2_lo10 | default | 192.168.0.15/32 |

##### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback10 | R2-PE2_lo10 | default | - |

#### Loopback Interfaces Device Configuration

```eos
!
interface Loopback10
   description R2-PE2_lo10
   no shutdown
   ip address 192.168.0.15/32
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
| 65102 | 192.168.0.15 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive | TTL Max Hops |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- | ------------ |
| 172.16.10.2 | 65000 | default | - | - | - | - | - | - | - | - | - |
| 172.16.12.2 | 65000 | default | - | - | - | - | - | - | - | - | - |
| 172.16.13.2 | 65000 | default | - | - | - | - | - | - | - | - | - |
| 172.16.14.2 | 65000 | default | - | - | - | - | - | - | - | - | - |

#### Router BGP Device Configuration

```eos
!
router bgp 65102
   router-id 192.168.0.15
   neighbor 172.16.10.2 remote-as 65000
   neighbor 172.16.10.2 description Edge10
   neighbor 172.16.12.2 remote-as 65000
   neighbor 172.16.12.2 description Edge12
   neighbor 172.16.13.2 remote-as 65000
   neighbor 172.16.13.2 description Edge13
   neighbor 172.16.14.2 remote-as 65000
   neighbor 172.16.14.2 description Edge14
   !
   address-family ipv4
      neighbor 172.16.10.2 prefix-list MPLS_IN in
      neighbor 172.16.10.2 activate
      neighbor 172.16.12.2 prefix-list MPLS_IN in
      neighbor 172.16.12.2 activate
      neighbor 172.16.13.2 prefix-list MPLS_IN in
      neighbor 172.16.13.2 activate
      neighbor 172.16.14.2 prefix-list MPLS_IN in
      neighbor 172.16.14.2 activate
      redistribute connected
```

## Filters

### Prefix-lists

#### Prefix-lists Summary

##### MPLS_IN

| Sequence | Action |
| -------- | ------ |
| 10 | permit 172.16.0.0/16 eq 24 |

#### Prefix-lists Device Configuration

```eos
!
ip prefix-list MPLS_IN
   seq 10 permit 172.16.0.0/16 eq 24
```
