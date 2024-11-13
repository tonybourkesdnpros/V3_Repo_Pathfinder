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
  - [Router BGP](#router-bgp)

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
| Ethernet7 | - | routed | - | 3.3.1.1/24 | default | 1500 | False | - | - |
| Ethernet8 | - | routed | - | 3.3.2.1/24 | default | 1500 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet7
   no shutdown
   mtu 1500
   no switchport
   ip address 3.3.1.1/24
!
interface Ethernet8
   no shutdown
   mtu 1500
   no switchport
   ip address 3.3.2.1/24
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback10 | ISP-3_lo10 | default | 192.168.0.75/32 |
| Loopback111 | Internet_Host | default | 1.1.1.1/32 |

##### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback10 | ISP-3_lo10 | default | - |
| Loopback111 | Internet_Host | default | - |

#### Loopback Interfaces Device Configuration

```eos
!
interface Loopback10
   description ISP-3_lo10
   no shutdown
   ip address 192.168.0.75/32
!
interface Loopback111
   description Internet_Host
   ip address 1.1.1.1/32
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
| 65002 | 192.168.0.75 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive | TTL Max Hops |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- | ------------ |
| 3.3.1.2 | 65103 | default | - | - | - | - | - | - | - | - | - |
| 3.3.2.2 | 65203 | default | - | - | - | - | - | - | - | - | - |

#### Router BGP Device Configuration

```eos
!
router bgp 65002
   router-id 192.168.0.75
   neighbor 3.3.1.2 remote-as 65103
   neighbor 3.3.1.2 description ISP-1
   neighbor 3.3.2.2 remote-as 65203
   neighbor 3.3.2.2 description ISP-2
   !
   address-family ipv4
      neighbor 3.3.1.2 activate
      neighbor 3.3.2.2 activate
      network 1.1.1.1/32
```
