# Validate State Report

**Table of Contents:**

- [Validate State Report](validate-state-report)
  - [Test Results Summary](#test-results-summary)
  - [Failed Test Results Summary](#failed-test-results-summary)
  - [All Test Results](#all-test-results)

## Test Results Summary

### Summary Totals

| Total Tests | Total Tests Passed | Total Tests Failed | Total Tests Skipped |
| ----------- | ------------------ | ------------------ | ------------------- |
| 368 | 306 | 54 | 8 |

### Summary Totals Device Under Test

| Device Under Test | Total Tests | Tests Passed | Tests Failed | Tests Skipped | Categories Failed | Categories Skipped |
| ------------------| ----------- | ------------ | ------------ | ------------- | ----------------- | ------------------ |
| Edge10 | 33 | 31 | 2 | 0 | Hardware | - |
| Edge12 | 33 | 31 | 2 | 0 | Hardware | - |
| Edge13 | 33 | 31 | 2 | 0 | Hardware | - |
| Edge14 | 33 | 31 | 2 | 0 | Hardware | - |
| Pathfinder1 | 26 | 24 | 2 | 0 | Hardware | - |
| Pathfinder2 | 26 | 24 | 2 | 0 | Hardware | - |
| Pathfinder3 | 26 | 5 | 17 | 4 | BGP, Interfaces, Security | Hardware |
| Pathfinder4 | 26 | 5 | 17 | 4 | BGP, Interfaces, Security | Hardware |
| Transit1 | 33 | 31 | 2 | 0 | Hardware | - |
| Transit2 | 33 | 31 | 2 | 0 | Hardware | - |
| Transit3 | 33 | 31 | 2 | 0 | Hardware | - |
| Transit4 | 33 | 31 | 2 | 0 | Hardware | - |

### Summary Totals Per Category

| Test Category | Total Tests | Tests Passed | Tests Failed | Tests Skipped |
| ------------- | ----------- | ------------ | ------------ | ------------- |
| BGP | 176 | 152 | 24 | 0 |
| Hardware | 48 | 20 | 20 | 8 |
| Interfaces | 60 | 56 | 4 | 0 |
| Routing | 12 | 12 | 0 | 0 |
| STUN | 16 | 16 | 0 | 0 |
| Security | 44 | 38 | 6 | 0 |
| System | 12 | 12 | 0 | 0 |

## Failed Test Results Summary

| ID | Device Under Test | Categories | Test | Description | Inputs | Result | Messages |
| -- | ----------------- | ---------- | ---- | ----------- | ------ | -------| -------- |
| 18 | Edge10 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 19 | Edge10 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 51 | Edge12 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 52 | Edge12 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 84 | Edge13 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 85 | Edge13 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 117 | Edge14 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 118 | Edge14 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 146 | Pathfinder1 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 147 | Pathfinder1 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 172 | Pathfinder2 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 173 | Pathfinder2 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 185 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 186 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 187 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.4': {'peerNotFound': True}}}}] |
| 188 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 189 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 190 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.4': {'peerNotFound': True}}}}] |
| 191 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 192 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 193 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.4': {'peerNotFound': True}}}}] |
| 194 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 195 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 196 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.4': {'peerNotFound': True}}}}] |
| 201 | Pathfinder3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | FAIL | The following interface(s) are not configured: ['Dps1'] |
| 205 | Pathfinder3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | FAIL | The following interface(s) are not configured: ['Vxlan1'] |
| 207 | Pathfinder3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.1'. |
| 208 | Pathfinder3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.2'. |
| 209 | Pathfinder3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.4'. |
| 211 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 212 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 213 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.3': {'peerNotFound': True}}}}] |
| 214 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 215 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 216 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.3': {'peerNotFound': True}}}}] |
| 217 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 218 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 219 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.3': {'peerNotFound': True}}}}] |
| 220 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 221 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 222 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.3': {'peerNotFound': True}}}}] |
| 227 | Pathfinder4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | FAIL | The following interface(s) are not configured: ['Dps1'] |
| 231 | Pathfinder4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | FAIL | The following interface(s) are not configured: ['Vxlan1'] |
| 233 | Pathfinder4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.1'. |
| 234 | Pathfinder4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.2'. |
| 235 | Pathfinder4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.3'. |
| 254 | Transit1 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 255 | Transit1 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 287 | Transit2 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 288 | Transit2 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 320 | Transit3 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 321 | Transit3 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 353 | Transit4 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 354 | Transit4 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |

## All Test Results

| ID | Device Under Test | Categories | Test | Description | Inputs | Result | Messages |
| -- | ----------------- | ---------- | ---- | ----------- | ------ | -------| -------- |
| 1 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 2 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 3 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 4 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 5 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 6 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 7 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 8 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 9 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 10 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 11 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 12 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 13 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 14 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 15 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 16 | Edge10 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 17 | Edge10 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 18 | Edge10 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 19 | Edge10 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 20 | Edge10 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 21 | Edge10 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 22 | Edge10 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet4 - mpls_r1 = 'up' | PASS | - |
| 23 | Edge10 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet5 - internet = 'up' | PASS | - |
| 24 | Edge10 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 25 | Edge10 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 26 | Edge10 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 27 | Edge10 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 28 | Edge10 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 29 | Edge10 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 30 | Edge10 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 31 | Edge10 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 11.11.10.2 Source Port: 4500 | PASS | - |
| 32 | Edge10 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 172.16.10.2 Source Port: 4500 | PASS | - |
| 33 | Edge10 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 34 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 35 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 36 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 37 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 38 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 39 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 40 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 41 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 42 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 43 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 44 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 45 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 46 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 47 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 48 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 49 | Edge12 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 50 | Edge12 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 51 | Edge12 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 52 | Edge12 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 53 | Edge12 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 54 | Edge12 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 55 | Edge12 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r1 = 'up' | PASS | - |
| 56 | Edge12 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 57 | Edge12 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 58 | Edge12 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 59 | Edge12 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 60 | Edge12 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 61 | Edge12 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 62 | Edge12 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 63 | Edge12 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 64 | Edge12 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 11.11.12.2 Source Port: 4500 | PASS | - |
| 65 | Edge12 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 172.16.12.2 Source Port: 4500 | PASS | - |
| 66 | Edge12 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 67 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 68 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 69 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 70 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 71 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 72 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 73 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 74 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 75 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 76 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 77 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 78 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 79 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 80 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 81 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 82 | Edge13 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 83 | Edge13 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 84 | Edge13 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 85 | Edge13 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 86 | Edge13 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 87 | Edge13 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 88 | Edge13 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r1 = 'up' | PASS | - |
| 89 | Edge13 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 90 | Edge13 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 91 | Edge13 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 92 | Edge13 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 93 | Edge13 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 94 | Edge13 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 95 | Edge13 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 96 | Edge13 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 97 | Edge13 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 11.11.13.2 Source Port: 4500 | PASS | - |
| 98 | Edge13 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 172.16.13.2 Source Port: 4500 | PASS | - |
| 99 | Edge13 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 100 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 101 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 102 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 103 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 104 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 105 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 106 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 107 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 108 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 109 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 110 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 111 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 112 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 113 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 114 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 115 | Edge14 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 116 | Edge14 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 117 | Edge14 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 118 | Edge14 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 119 | Edge14 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 120 | Edge14 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 121 | Edge14 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r1 = 'up' | PASS | - |
| 122 | Edge14 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 123 | Edge14 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 124 | Edge14 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 125 | Edge14 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 126 | Edge14 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 127 | Edge14 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 128 | Edge14 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 129 | Edge14 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 130 | Edge14 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 11.11.14.2 Source Port: 4500 | PASS | - |
| 131 | Edge14 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 172.16.14.2 Source Port: 4500 | PASS | - |
| 132 | Edge14 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 133 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 134 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 135 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 136 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 137 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 138 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 139 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 140 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 141 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 142 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 143 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 144 | Pathfinder1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 145 | Pathfinder1 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 146 | Pathfinder1 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 147 | Pathfinder1 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 148 | Pathfinder1 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 149 | Pathfinder1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 150 | Pathfinder1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r1 = 'up' | PASS | - |
| 151 | Pathfinder1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 152 | Pathfinder1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 153 | Pathfinder1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 154 | Pathfinder1 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 155 | Pathfinder1 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 156 | Pathfinder1 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 157 | Pathfinder1 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 158 | Pathfinder1 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 159 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 160 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 161 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 162 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 163 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 164 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 165 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 166 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 167 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 168 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 169 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 170 | Pathfinder2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 171 | Pathfinder2 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 172 | Pathfinder2 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 173 | Pathfinder2 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 174 | Pathfinder2 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 175 | Pathfinder2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 176 | Pathfinder2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r1 = 'up' | PASS | - |
| 177 | Pathfinder2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 178 | Pathfinder2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 179 | Pathfinder2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 180 | Pathfinder2 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 181 | Pathfinder2 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 182 | Pathfinder2 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 183 | Pathfinder2 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 184 | Pathfinder2 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 185 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 186 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 187 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.4': {'peerNotFound': True}}}}] |
| 188 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 189 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 190 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.4': {'peerNotFound': True}}}}] |
| 191 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 192 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 193 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.4': {'peerNotFound': True}}}}] |
| 194 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 195 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 196 | Pathfinder3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.4': {'peerNotFound': True}}}}] |
| 197 | Pathfinder3 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentCooling test is not supported on vEOS-lab. |
| 198 | Pathfinder3 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentPower test is not supported on vEOS-lab. |
| 199 | Pathfinder3 | Hardware | VerifyTemperature | Verifies the device temperature. | - | SKIPPED | VerifyTemperature test is not supported on vEOS-lab. |
| 200 | Pathfinder3 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | SKIPPED | VerifyTransceiversManufacturers test is not supported on vEOS-lab. |
| 201 | Pathfinder3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | FAIL | The following interface(s) are not configured: ['Dps1'] |
| 202 | Pathfinder3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r2 = 'up' | PASS | - |
| 203 | Pathfinder3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 204 | Pathfinder3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 205 | Pathfinder3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | FAIL | The following interface(s) are not configured: ['Vxlan1'] |
| 206 | Pathfinder3 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 207 | Pathfinder3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.1'. |
| 208 | Pathfinder3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.2'. |
| 209 | Pathfinder3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.4'. |
| 210 | Pathfinder3 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 211 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 212 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 213 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | FAIL | Failures: [{'afi': 'evpn', 'vrfs': {'default': {'10.99.102.3': {'peerNotFound': True}}}}] |
| 214 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 215 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 216 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | FAIL | Failures: [{'afi': 'ipv4', 'safi': 'sr-te', 'vrfs': {'default': {'10.99.102.3': {'peerNotFound': True}}}}] |
| 217 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 218 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 219 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | FAIL | Failures: [{'afi': 'link-state', 'vrfs': {'default': {'10.99.102.3': {'peerNotFound': True}}}}] |
| 220 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.1': {'peerNotFound': True}}}}] |
| 221 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.2': {'peerNotFound': True}}}}] |
| 222 | Pathfinder4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | FAIL | Failures: [{'afi': 'path-selection', 'vrfs': {'default': {'10.99.102.3': {'peerNotFound': True}}}}] |
| 223 | Pathfinder4 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentCooling test is not supported on vEOS-lab. |
| 224 | Pathfinder4 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentPower test is not supported on vEOS-lab. |
| 225 | Pathfinder4 | Hardware | VerifyTemperature | Verifies the device temperature. | - | SKIPPED | VerifyTemperature test is not supported on vEOS-lab. |
| 226 | Pathfinder4 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | SKIPPED | VerifyTransceiversManufacturers test is not supported on vEOS-lab. |
| 227 | Pathfinder4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | FAIL | The following interface(s) are not configured: ['Dps1'] |
| 228 | Pathfinder4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r2 = 'up' | PASS | - |
| 229 | Pathfinder4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 230 | Pathfinder4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 231 | Pathfinder4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | FAIL | The following interface(s) are not configured: ['Vxlan1'] |
| 232 | Pathfinder4 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 233 | Pathfinder4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.1'. |
| 234 | Pathfinder4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.2'. |
| 235 | Pathfinder4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | FAIL | No IPv4 security connection configured for peer '10.99.102.3'. |
| 236 | Pathfinder4 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 237 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 238 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 239 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 240 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 241 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 242 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 243 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 244 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 245 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 246 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 247 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 248 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 249 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 250 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 251 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 252 | Transit1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 253 | Transit1 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 254 | Transit1 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 255 | Transit1 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 256 | Transit1 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 257 | Transit1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 258 | Transit1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r1 = 'up' | PASS | - |
| 259 | Transit1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 260 | Transit1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 261 | Transit1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 262 | Transit1 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 263 | Transit1 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 264 | Transit1 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 265 | Transit1 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 266 | Transit1 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 267 | Transit1 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 11.11.51.2 Source Port: 4500 | PASS | - |
| 268 | Transit1 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 172.16.51.2 Source Port: 4500 | PASS | - |
| 269 | Transit1 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 270 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 271 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 272 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 273 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 274 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 275 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 276 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 277 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 278 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 279 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 280 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 281 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 282 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 283 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 284 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 285 | Transit2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 286 | Transit2 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 287 | Transit2 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 288 | Transit2 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 289 | Transit2 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 290 | Transit2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 291 | Transit2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - internet = 'up' | PASS | - |
| 292 | Transit2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - mpls_r1 = 'up' | PASS | - |
| 293 | Transit2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 294 | Transit2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 295 | Transit2 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 296 | Transit2 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 297 | Transit2 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 298 | Transit2 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 299 | Transit2 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 300 | Transit2 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 11.11.52.2 Source Port: 4500 | PASS | - |
| 301 | Transit2 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 172.16.52.2 Source Port: 4500 | PASS | - |
| 302 | Transit2 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 303 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 304 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 305 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 306 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 307 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 308 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 309 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 310 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 311 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 312 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 313 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 314 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 315 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 316 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 317 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 318 | Transit3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 319 | Transit3 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 320 | Transit3 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 321 | Transit3 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 322 | Transit3 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 323 | Transit3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 324 | Transit3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - mpls_r2 = 'up' | PASS | - |
| 325 | Transit3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - internet = 'up' | PASS | - |
| 326 | Transit3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 327 | Transit3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 328 | Transit3 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 329 | Transit3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 330 | Transit3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 331 | Transit3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 332 | Transit3 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 333 | Transit3 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 172.16.53.2 Source Port: 4500 | PASS | - |
| 334 | Transit3 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 22.22.53.2 Source Port: 4500 | PASS | - |
| 335 | Transit3 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 336 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 337 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 338 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 339 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 340 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 341 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 342 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 343 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 SR-TE Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 344 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 345 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 346 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 347 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Link-State Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 348 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder1 (IP: 10.99.102.1) | PASS | - |
| 349 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder2 (IP: 10.99.102.2) | PASS | - |
| 350 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder3 (IP: 10.99.102.3) | PASS | - |
| 351 | Transit4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP Path-Selection Peer: Pathfinder4 (IP: 10.99.102.4) | PASS | - |
| 352 | Transit4 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | PASS | - |
| 353 | Transit4 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | FAIL | ValueError: "AntaCommand" object has no field "failed" |
| 354 | Transit4 | Hardware | VerifyTemperature | Verifies the device temperature. | - | FAIL | Device temperature exceeds acceptable limits. Current system status: 'unknownTemperatureAlarmLevel' |
| 355 | Transit4 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | PASS | - |
| 356 | Transit4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Dps1 - DPS Interface = 'up' | PASS | - |
| 357 | Transit4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - internet = 'up' | PASS | - |
| 358 | Transit4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - mpls_r2 = 'up' | PASS | - |
| 359 | Transit4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - Router_ID = 'up' | PASS | - |
| 360 | Transit4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 361 | Transit4 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 362 | Transit4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.1 VRF: default | PASS | - |
| 363 | Transit4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.2 VRF: default | PASS | - |
| 364 | Transit4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.3 VRF: default | PASS | - |
| 365 | Transit4 | Security | VerifySpecificIPSecConn | Verifies IPv4 security connections for a peer. | IPv4 Peer: 10.99.102.4 VRF: default | PASS | - |
| 366 | Transit4 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 172.16.54.2 Source Port: 4500 | PASS | - |
| 367 | Transit4 | STUN | VerifyStunClient | Verifies the STUN client is configured with the specified IPv4 source address and port. Validate the public IP and port if provided. | Source IPv4 Address: 22.22.54.2 Source Port: 4500 | PASS | - |
| 368 | Transit4 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
