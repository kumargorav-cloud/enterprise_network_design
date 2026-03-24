# 🌐 Enterprise Network Design with OSPF, VLANs & NAT (PAT)

## 📌 Project Overview

This project demonstrates a scalable enterprise network design using:

* Multi-layer switching
* Dynamic routing with OSPF
* VLAN segmentation
* Inter-VLAN routing
* NAT (PAT) for internet access
* Redundant ISP connectivity

The goal is to simulate a real-world enterprise network with high availability, segmentation, and external connectivity.

---

## 🏗️ Network Architecture

### 🔹 Devices Used

* 2 × Multilayer Switches (Core/Distribution Layer)
* 2 × Internal Routers
* 2 × ISP Routers
* End devices (PCs, Servers)

---

## 🌐 Key Features

### 🔸 VLAN Segmentation

VLANs created for department-wise isolation:

| VLAN ID | Department               |
| ------- | ------------------------ |
| 10      | Sales & Marketing        |
| 20      | HR & Logistics           |
| 30      | Finance & Accounts       |
| 40      | Admin & Public Relations |
| 50      | ICT                      |
| 60      | Server Room              |

---

### 🔸 Inter-VLAN Routing

* Implemented using **Multilayer Switch (SVIs)**
* Each VLAN has a default gateway configured on the L3 switch
* Enables communication between departments

---

### 🔸 Dynamic Routing (OSPF)

* Routing protocol: **OSPF (Open Shortest Path First)**
* Configured on both internal routers
* Ensures:

  * Fast convergence
  * Scalable routing
  * Efficient path selection

#### OSPF Design:

* Area: 0 (Backbone Area)
* Advertises all internal networks
* Provides redundancy between routers

---

### 🔸 NAT (PAT) Configuration

* Implemented on edge routers
* Allows multiple private IPs to share a single public IP

#### Purpose:

* Internet access for internal users
* IP conservation
* Security (hides internal network)

---

### 🔸 ISP Redundancy

* Connected to **2 ISP routers**
* Provides:

  * Failover capability
  * High availability
  * Load sharing (optional)

---

## 🧩 IP Addressing Scheme

* Base Network: `172.16.0.0/16`
* Subnetting:

  * `/25` → Departments
  * `/28` → Server Room

Example:

* VLAN 10 → 172.16.1.0/25
* VLAN 20 → 172.16.1.128/25
* VLAN 60 → 172.16.3.128/28

---

## 🔄 Traffic Flow

1. PC → VLAN Gateway (SVI on L3 Switch)
2. L3 Switch → Internal Router
3. Router → ISP Router
4. NAT (PAT) applied
5. Traffic reaches Internet

---

## ⚙️ Technologies Used

* VLANs (802.1Q)
* Inter-VLAN Routing (SVI)
* OSPF (Dynamic Routing)
* NAT Overload (PAT)
* Static & Default Routing
* Layer 2 & Layer 3 Switching

---

---

## 🚀 Learning Outcomes

* Designed a hierarchical network (Core + Distribution)
* Implemented VLAN segmentation and routing
* Configured OSPF for dynamic routing
* Enabled internet access using NAT (PAT)
* Built redundancy using dual ISP architecture


## 📂 Packet Tracer File

👉 [Download from Google Drive](https://drive.google.com/file/d/16RWo2_tnjk9BIfMoiYNa3_0LiMvyxd2k/view?usp=drive_link)


---
