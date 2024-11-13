# Edge10

## Table of Contents

- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
  - [Loopback Interfaces](#loopback-interfaces)
- [Routing](#routing)
  - [IP Routing](#ip-routing)
  - [IPv6 Routing](#ipv6-routing)
  - [Router OSPF](#router-ospf)
  - [Router BGP](#router-bgp)
- [VRF Instances](#vrf-instances)
  - [VRF Instances Summary](#vrf-instances-summary)
  - [VRF Instances Device Configuration](#vrf-instances-device-configuration)

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
| Ethernet3 | - | routed | - | 10.251.10.1/24 | VRF_A | 1500 | False | - | - |
| Ethernet4 | - | routed | - | 172.16.10.2/24 | default | 1500 | False | - | - |
| Ethernet5 | - | routed | - | 11.11.10.2/24 | default | 1500 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   shutdown
   no switchport
!
interface Ethernet2
   shutdown
   no switchport
!
interface Ethernet3
   no shutdown
   mtu 1500
   no switchport
   vrf VRF_A
   ip address 10.251.10.1/24
   ip ospf network point-to-point
   ip ospf area 0
!
interface Ethernet4
   no shutdown
   mtu 1500
   no switchport
   ip address 172.16.10.2/24
!
interface Ethernet5
   no shutdown
   mtu 1500
   no switchport
   ip address 11.11.10.2/24
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback10 | Edge-10_l10 | default | 192.168.0.10/32 |

##### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback10 | Edge-10_l10 | default | - |

#### Loopback Interfaces Device Configuration

```eos
!
interface Loopback10
   description Edge-10_l10
   no shutdown
   ip address 192.168.0.10/32
```

## Routing

### IP Routing

#### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | True |
| VRF_A | True |

#### IP Routing Device Configuration

```eos
!
ip routing
ip routing vrf VRF_A
```

### IPv6 Routing

#### IPv6 Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | False |
| VRF_A | false |

### Router OSPF

#### Router OSPF Summary

| Process ID | Router ID | Default Passive Interface | No Passive Interface | BFD | Max LSA | Default Information Originate | Log Adjacency Changes Detail | Auto Cost Reference Bandwidth | Maximum Paths | MPLS LDP Sync Default | Distribute List In |
| ---------- | --------- | ------------------------- | -------------------- | --- | ------- | ----------------------------- | ---------------------------- | ----------------------------- | ------------- | --------------------- | ------------------ |
| 10 | 192.168.0.10 | disabled |- | disabled | default | Always | disabled | - | - | - | - |

#### Router OSPF Router Redistribution

| Process ID | Source Protocol | Include Leaked | Route Map |
| ---------- | --------------- | -------------- | --------- |
| 10 | bgp | disabled | - |

#### OSPF Interfaces

| Interface | Area | Cost | Point To Point |
| -------- | -------- | -------- | -------- |
| Ethernet3 | 0 | - | True |

#### Router OSPF Device Configuration

```eos
!
router ospf 10 vrf VRF_A
   router-id 192.168.0.10
   default-information originate always
   redistribute bgp
```

### Router BGP

ASN Notation: asplain

#### Router BGP Summary

| BGP AS | Router ID |
| ------ | --------- |
| 65000 | 192.168.0.10 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive | TTL Max Hops |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- | ------------ |
| 11.11.10.1 | 65103 | default | - | - | - | - | - | - | - | - | - |
| 172.16.10.1 | 65102 | default | - | - | - | - | - | - | - | - | - |

#### Router BGP VRFs

| VRF | Route-Distinguisher | Redistribute |
| --- | ------------------- | ------------ |
| VRF_A | - | connected<br>ospf |

#### Router BGP Device Configuration

```eos
!
router bgp 65000
   router-id 192.168.0.10
   neighbor 11.11.10.1 remote-as 65103
   neighbor 11.11.10.1 description ISP-1
   neighbor 172.16.10.1 remote-as 65102
   neighbor 172.16.10.1 description R1_MPLS
   !
   address-family ipv4
      neighbor 11.11.10.1 route-map INTERNET_OUT out
      neighbor 11.11.10.1 activate
      neighbor 172.16.10.1 prefix-list MPLS_OUT out
      neighbor 172.16.10.1 activate
      redistribute connected
   !
   vrf VRF_A
      redistribute connected
      redistribute ospf
```

## VRF Instances

### VRF Instances Summary

| VRF Name | IP Routing |
| -------- | ---------- |
| VRF_A | enabled |

### VRF Instances Device Configuration

```eos
!
vrf instance VRF_A
```
