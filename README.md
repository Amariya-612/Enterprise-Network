# Enterprise Network Design Using VLSM and VLAN

## 1. Introduction

This project is a simple academic **Enterprise Network Design** created using **Cisco Packet Tracer**.

The purpose of the project is to design a network using **VLSM subnetting, VLANs, trunking, and inter-VLAN routing**.

The network is designed from the IP address:

`192.168.17.0/24`

The network is divided into **9 subnets** based on the required number of hosts.

## 2. Network Devices

The topology contains:

* 1 Router
* 1 Core Switch
* 3 Distribution Switches
* 9 Access Switches
* Multiple PCs

**No server is used in this network.**

## 3. Network Requirements

The original requirement is:

* 3 networks with 20 hosts each
* 2 networks with 12 hosts each
* 4 networks with 5 hosts each

VLSM is used to divide the `192.168.17.0/24` network efficiently.

### VLSM Calculation

| Required Hosts | Subnet | Usable Hosts |
| -------------: | -----: | -----------: |
|             20 |    /27 |           30 |
|             12 |    /28 |           14 |
|              5 |    /29 |            6 |

## 4. IP Addressing and VLAN Table

| VLAN    | Network           | Default Gateway | Usable Host Range             | Broadcast      |
| ------- | ----------------- | --------------- | ----------------------------- | -------------- |
| VLAN 10 | 192.168.17.0/27   | 192.168.17.1    | 192.168.17.2–192.168.17.30    | 192.168.17.31  |
| VLAN 20 | 192.168.17.32/27  | 192.168.17.33   | 192.168.17.34–192.168.17.62   | 192.168.17.63  |
| VLAN 30 | 192.168.17.64/27  | 192.168.17.65   | 192.168.17.66–192.168.17.94   | 192.168.17.95  |
| VLAN 40 | 192.168.17.96/28  | 192.168.17.97   | 192.168.17.98–192.168.17.110  | 192.168.17.111 |
| VLAN 50 | 192.168.17.112/28 | 192.168.17.113  | 192.168.17.114–192.168.17.126 | 192.168.17.127 |
| VLAN 60 | 192.168.17.128/29 | 192.168.17.129  | 192.168.17.130–192.168.17.134 | 192.168.17.135 |
| VLAN 70 | 192.168.17.136/29 | 192.168.17.137  | 192.168.17.138–192.168.17.142 | 192.168.17.143 |
| VLAN 80 | 192.168.17.144/29 | 192.168.17.145  | 192.168.17.146–192.168.17.150 | 192.168.17.151 |
| VLAN 90 | 192.168.17.152/29 | 192.168.17.153  | 192.168.17.154–192.168.17.158 | 192.168.17.159 |

<img width="515" height="335" alt="net" src="https://github.com/user-attachments/assets/177d128c-4194-4a34-a64c-3aa2202e5bee" />


### Network Layers

**Core Layer**

The core switch provides the main connection between the router and the distribution switches.

**Distribution Layer**

Three distribution switches connect the core layer to the access layer.

**Access Layer**

Nine access switches connect the end-user PCs to the enterprise network.

## 5. VLANs

The network uses nine VLANs:

```text
VLAN 10
VLAN 20
VLAN 30
VLAN 40
VLAN 50
VLAN 60
VLAN 70
VLAN 80
VLAN 90
```

Each VLAN has its own subnet and default gateway.

This provides network segmentation and separates different groups of users.

## 6. Trunking

Trunk links are used between network devices to carry traffic for multiple VLANs.

Trunk connections are used between:

* Router and Core Switch
* Core Switch and Distribution Switches
* Distribution Switches and Access Switches

IEEE 802.1Q is used for VLAN trunking.

## 7. Inter-VLAN Routing

The router provides communication between the different VLANs using **Router-on-a-Stick**.

The default gateways are:

```text
VLAN 10 → 192.168.17.1
VLAN 20 → 192.168.17.33
VLAN 30 → 192.168.17.65
VLAN 40 → 192.168.17.97
VLAN 50 → 192.168.17.113
VLAN 60 → 192.168.17.129
VLAN 70 → 192.168.17.137
VLAN 80 → 192.168.17.145
VLAN 90 → 192.168.17.153
```

## 8. Main Configuration Tasks

The project includes:

* VLSM subnetting
* VLAN creation
* VLAN assignment
* Access port configuration
* Trunk port configuration
* Router-on-a-Stick
* Inter-VLAN routing
* Core switch configuration
* Distribution switch configuration
* Access switch configuration
* PC IP configuration
* Connectivity testing

## 9. Verification Commands

### Check VLANs

```bash
show vlan brief
```

### Check Trunk Ports

```bash
show interfaces trunk
```

### Check Interfaces

```bash
show ip interface brief
```

### Check Routing Table

```bash
show ip route
```

### Test Connectivity

```bash
ping <destination-ip>
```

## 10. Project Objectives

The main objectives of this project are:

1. To understand VLSM subnetting.
2. To divide a `/24` network into different subnet sizes.
3. To create and configure VLANs.
4. To configure trunk links.
5. To implement inter-VLAN routing.
6. To understand hierarchical enterprise network design.
7. To configure Cisco networking devices using IOS commands.
8. To test and troubleshoot network connectivity.

## 11. Technologies Used

* Cisco Packet Tracer
* Cisco IOS
* IPv4
* VLSM
* VLAN
* 802.1Q Trunking
* Router-on-a-Stick
* Inter-VLAN Routing
* Ethernet

## 12. Conclusion

This project demonstrates the design of a basic **enterprise network** using Cisco Packet Tracer.

The `192.168.17.0/24` network is divided into nine VLSM subnets and assigned to VLANs 10–90. The hierarchical topology uses a core switch, distribution switches, and access switches to organize the network.

VLANs provide logical separation between users, while trunking allows multiple VLANs to travel between switches. Router-on-a-Stick provides communication between different VLANs.

The project provides practical experience in **IP addressing, VLSM, VLANs, trunking, inter-VLAN routing, and enterprise network design**.

---

**Project Type:** Academic Networking Project
**Platform:** Cisco Packet Tracer
**Network:** `192.168.17.0/24`
**VLANs:** 10–90
**Server:** None
