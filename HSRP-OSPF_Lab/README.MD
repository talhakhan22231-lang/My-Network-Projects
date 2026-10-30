# HSRP & OSPF Redundancy Lab (Cisco GNS3)

## 📌 Project Overview
This lab demonstrates a highly available enterprise network topology. It combines **OSPF (Open Shortest Path First)** for dynamic routing with **HSRP (Hot Standby Router Protocol)** to provide gateway redundancy for end devices. 

The goal of this lab was to ensure that if the primary gateway (R1) fails, the network seamlessly fails over to the standby gateway (R2) without manual intervention.

## 🗺️ Topology & Addressing
*   **Routing Protocol:** OSPF Process 10, Area 1
*   **HSRP Group:** 1
*   **HSRP Virtual IP:** `13.1.1.30`
*   **R1 (Active Gateway):** Physical IP `13.1.1.10`, Priority 203, Preempt enabled.
*   **R2 (Standby Gateway):** Physical IP `13.1.1.20`, Priority 100, Preempt enabled.
*   **R3 (Core Router):** Serial connections to R1 & R2, advertising Loopbacks `192.168.20.1` and `192.168.30.1`.
*   **R4 & R5 (End Devices):** Configured as PCs using `no ip routing`.

## 🛠️ Complete Configuration Guide

### 1. R1 Configuration (Active Gateway + OSPF)
```cisco
R1> enable
R1# configure terminal
! Interface IPs
R1(config)# interface ethernet 0/0
R1(config-if)# ip address 13.1.1.10 255.255.255.0
R1(config-if)# no shutdown
R1(config-if)# interface serial 0/0
R1(config-if)# ip address 10.0.0.1 255.255.255.252
R1(config-if)# no shutdown
R1(config-if)# exit

! HSRP Configuration
R1(config)# interface ethernet 0/0
R1(config-if)# standby 1 ip 13.1.1.30
R1(config-if)# standby 1 priority 203
R1(config-if)# standby 1 preempt

! OSPF Configuration
R1(config)# router ospf 10
R1(config-router)# network 13.1.1.0 0.0.0.255 area 1
R1(config-router)# network 10.0.0.0 0.0.0.3 area 1
