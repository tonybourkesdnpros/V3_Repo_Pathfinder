# ISP-3

## Table of Contents

- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
  - [Loopback Interfaces](#loopback-interfaces)
- [Routing](#routing)
  - [IP Routing](#ip-routing)
  - [Static Routes](#static-routes)
  - [Router BGP](#router-bgp)
- [Filters](#filters)
  - [Prefix-lists](#prefix-lists)
  - [Route-maps](#route-maps)

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
| Ethernet1 | - | routed | - | 192.51.75.2/24 | default | 1500 | True | - | - |
| Ethernet2 | - | routed | - | 192.52.75.2/24 | default | 1500 | True | - | - |
| Ethernet3 | - | routed | - | 192.54.75.2/24 | default | 1500 | True | - | - |
| Ethernet4 | - | routed | - | 192.53.75.2/24 | default | 1500 | True | - | - |
| Ethernet7 | - | routed | - | 192.16.75.2/24 | default | 1500 | False | - | - |
| Ethernet8 | - | routed | - | 192.26.75.2/24 | default | 1500 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   shutdown
   mtu 1500
   no switchport
   ip address 192.51.75.2/24
!
interface Ethernet2
   shutdown
   mtu 1500
   no switchport
   ip address 192.52.75.2/24
!
interface Ethernet3
   shutdown
   mtu 1500
   no switchport
   ip address 192.54.75.2/24
!
interface Ethernet4
   shutdown
   mtu 1500
   no switchport
   ip address 192.53.75.2/24
!
interface Ethernet5
   shutdown
   mtu 1500
   no switchport
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
   ip address 192.16.75.2/24
!
interface Ethernet8
   no shutdown
   mtu 1500
   no switchport
   ip address 192.26.75.2/24
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback10 | ISP-3_lo10 | default | 192.168.0.75/32 |

##### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback10 | ISP-3_lo10 | default | - |

#### Loopback Interfaces Device Configuration

```eos
!
interface Loopback10
   description ISP-3_lo10
   no shutdown
   ip address 192.168.0.75/32
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

### Static Routes

#### Static Routes Summary

| VRF | Destination Prefix | Next Hop IP | Exit interface | Administrative Distance | Tag | Route Name | Metric |
| --- | ------------------ | ----------- | -------------- | ----------------------- | --- | ---------- | ------ |
| default | 0.0.0.0/0 | - | Null0 | 1 | - | - | - |

#### Static Routes Device Configuration

```eos
!
ip route 0.0.0.0/0 Null0
```

### Router BGP

ASN Notation: asplain

#### Router BGP Summary

| BGP AS | Router ID |
| ------ | --------- |
| 65002 | 192.168.0.75 |

#### Router BGP Peer Groups

##### R1Internet

| Settings | Value |
| -------- | ----- |
| Remote AS | 65103 |

##### R2Internet

| Settings | Value |
| -------- | ----- |
| Remote AS | 65203 |

##### REGION1

| Settings | Value |
| -------- | ----- |
| Allowas-in | Allowed, allowed 3 (default) times |
| Remote AS | 65000 |

##### REGION2

| Settings | Value |
| -------- | ----- |
| Allowas-in | Allowed, allowed 3 (default) times |
| Remote AS | 65000 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive | TTL Max Hops |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- | ------------ |
| 192.16.75.1 | Inherited from peer group R1Internet | default | - | - | - | - | - | - | - | - | - |
| 192.26.75.1 | Inherited from peer group R2Internet | default | - | - | - | - | - | - | - | - | - |
| 192.51.75.1 | Inherited from peer group REGION1 | default | - | - | - | Inherited from peer group REGION1 | - | - | - | - | - |
| 192.52.75.1 | Inherited from peer group REGION1 | default | - | - | - | Inherited from peer group REGION1 | - | - | - | - | - |
| 192.53.75.1 | Inherited from peer group REGION2 | default | - | - | - | Inherited from peer group REGION2 | - | - | - | - | - |
| 192.54.75.1 | Inherited from peer group REGION2 | default | - | - | - | Inherited from peer group REGION2 | - | - | - | - | - |

#### Router BGP Device Configuration

```eos
!
router bgp 65002
   router-id 192.168.0.75
   neighbor R1Internet peer group
   neighbor R1Internet remote-as 65103
   neighbor R2Internet peer group
   neighbor R2Internet remote-as 65203
   neighbor REGION1 peer group
   neighbor REGION1 remote-as 65000
   neighbor REGION1 allowas-in
   neighbor REGION2 peer group
   neighbor REGION2 remote-as 65000
   neighbor REGION2 allowas-in
   neighbor 192.16.75.1 peer group R1Internet
   neighbor 192.26.75.1 peer group R2Internet
   neighbor 192.51.75.1 peer group REGION1
   neighbor 192.52.75.1 peer group REGION1
   neighbor 192.53.75.1 peer group REGION2
   neighbor 192.54.75.1 peer group REGION2
   !
   address-family ipv4
      neighbor R1Internet activate
      neighbor R2Internet activate
      neighbor REGION1 route-map DEFAULTONLY out
      no neighbor REGION1 activate
      neighbor REGION2 route-map DEFAULTONLY out
      no neighbor REGION2 activate
      network 0.0.0.0/0
      network 192.168.0.75/32
      redistribute connected
```

## Filters

### Prefix-lists

#### Prefix-lists Summary

##### DEFAULTONLY

| Sequence | Action |
| -------- | ------ |
| 10 | permit 0.0.0.0/0 |

#### Prefix-lists Device Configuration

```eos
!
ip prefix-list DEFAULTONLY
   seq 10 permit 0.0.0.0/0
```

### Route-maps

#### Route-maps Summary

##### DEFAULTONLY

| Sequence | Type | Match | Set | Sub-Route-Map | Continue |
| -------- | ---- | ----- | --- | ------------- | -------- |
| 10 | permit | ip address prefix-list DEFAULTONLY | - | - | - |

#### Route-maps Device Configuration

```eos
!
route-map DEFAULTONLY permit 10
   match ip address prefix-list DEFAULTONLY
```
