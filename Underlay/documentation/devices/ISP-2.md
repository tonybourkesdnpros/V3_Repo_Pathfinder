# ISP-2

## Table of Contents

- [DHCP Server](#dhcp-server)
  - [DHCP Servers Summary](#dhcp-servers-summary)
  - [DHCP Server Configuration](#dhcp-server-configuration)
  - [DHCP Server Interfaces](#dhcp-server-interfaces)
- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
  - [Loopback Interfaces](#loopback-interfaces)
- [Routing](#routing)
  - [IP Routing](#ip-routing)
  - [Router BGP](#router-bgp)

## DHCP Server

### DHCP Servers Summary

| DHCP Server Enabled | VRF | IPv4 DNS Domain | IPv4 DNS Servers | IPv4 Bootfile | IPv4 Lease Time | IPv6 DNS Domain | IPv6 DNS Servers | IPv6 Bootfile | IPv6 Lease Time |
| ------------------- | --- | --------------- | ---------------- | ------------- | --------------- | --------------- | ---------------- | ------------- | --------------- |
| True | default | - | 192.168.0.1 | - | - | - | - | - | - |

#### VRF default DHCP Server

##### Subnets

| Subnet | Name | DNS Servers | Default Gateway | Lease Time | Ranges |
| ------ | ---- | ----------- | --------------- | ---------- | ------ |
| 22.22.20.0/24 | To_Edge_20 | 192.168.0.1 | 22.22.20.1 | - | 22.22.20.10-22.22.20.20 |
| 22.22.21.0/24 | To_Edge_21 | 192.168.0.1 | 22.22.21.1 | - | 22.22.21.10-22.22.21.20 |
| 22.22.22.0/24 | To_Edge_22 | 192.168.0.1 | 22.22.22.1 | - | 22.22.22.10-22.22.22.20 |
| 22.22.23.0/24 | To_Edge_23 | 192.168.0.1 | 22.22.23.1 | - | 22.22.23.10-22.22.23.20 |
| 22.22.24.0/24 | To_Edge_24 | 192.168.0.1 | 22.22.24.1 | - | 22.22.24.10-22.22.24.20 |

### DHCP Server Configuration

```eos
!
dhcp server
   dns server ipv4 192.168.0.1
   !
   subnet 22.22.20.0/24
      !
      range 22.22.20.10 22.22.20.20
      name To_Edge_20
      dns server 192.168.0.1
      default-gateway 22.22.20.1
   !
   subnet 22.22.21.0/24
      !
      range 22.22.21.10 22.22.21.20
      name To_Edge_21
      dns server 192.168.0.1
      default-gateway 22.22.21.1
   !
   subnet 22.22.22.0/24
      !
      range 22.22.22.10 22.22.22.20
      name To_Edge_22
      dns server 192.168.0.1
      default-gateway 22.22.22.1
   !
   subnet 22.22.23.0/24
      !
      range 22.22.23.10 22.22.23.20
      name To_Edge_23
      dns server 192.168.0.1
      default-gateway 22.22.23.1
   !
   subnet 22.22.24.0/24
      !
      range 22.22.24.10 22.22.24.20
      name To_Edge_24
      dns server 192.168.0.1
      default-gateway 22.22.24.1
```

### DHCP Server Interfaces

| Interface name | DHCP IPv4 | DHCP IPv6 |
| -------------- | --------- | --------- |
| Ethernet5 | True | False |
| Ethernet6 | True | False |
| Ethernet7 | True | False |
| Ethernet8 | True | False |
| Ethernet9 | True | False |

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
| Ethernet1 | - | routed | - | 22.22.53.1/24 | default | 1500 | False | - | - |
| Ethernet2 | - | routed | - | 22.22.54.1/24 | default | 1500 | False | - | - |
| Ethernet3 | - | routed | - | 22.22.3.1/24 | default | 1500 | False | - | - |
| Ethernet4 | - | routed | - | 22.22.4.1/24 | default | 1500 | False | - | - |
| Ethernet5 | - | routed | - | 22.22.20.1/24 | default | 1500 | False | - | - |
| Ethernet6 | - | routed | - | 22.22.21.1/24 | default | 1500 | False | - | - |
| Ethernet7 | - | routed | - | 22.22.22.1/24 | default | 1500 | False | - | - |
| Ethernet8 | - | routed | - | 22.22.23.1/24 | default | 1500 | False | - | - |
| Ethernet9 | - | routed | - | 22.22.24.1/24 | default | 1500 | False | - | - |
| Ethernet10 | - | routed | - | 3.3.2.2/24 | default | 1500 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.53.1/24
!
interface Ethernet2
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.54.1/24
!
interface Ethernet3
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.3.1/24
!
interface Ethernet4
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.4.1/24
!
interface Ethernet5
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.20.1/24
   dhcp server ipv4
!
interface Ethernet6
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.21.1/24
   dhcp server ipv4
!
interface Ethernet7
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.22.1/24
   dhcp server ipv4
!
interface Ethernet8
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.23.1/24
   dhcp server ipv4
!
interface Ethernet9
   no shutdown
   mtu 1500
   no switchport
   ip address 22.22.24.1/24
   dhcp server ipv4
!
interface Ethernet10
   no shutdown
   mtu 1500
   no switchport
   ip address 3.3.2.2/24
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback10 | ISP_lo10 | default | 192.168.0.26/32 |

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
   ip address 192.168.0.26/32
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
| 65203 | 192.168.0.26 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive | TTL Max Hops |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- | ------------ |
| 3.3.2.1 | 65002 | default | - | - | - | - | - | - | - | - | - |

#### Router BGP Device Configuration

```eos
!
router bgp 65203
   router-id 192.168.0.26
   neighbor 3.3.2.1 remote-as 65002
   neighbor 3.3.2.1 description IPS-3
   !
   address-family ipv4
      neighbor 3.3.2.1 activate
      redistribute connected
```
