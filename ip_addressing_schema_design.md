# 📡 IP Addressing Scheme Design

## 📌 Project Overview

This project documents a structured IP addressing and subnetting scheme for a multi-floor organizational network.

The design ensures:

* Efficient IP utilization
* Logical segmentation by department
* Improved security and broadcast control
* Scalability for future expansion

---

## 🌐 Base Network

```
Network Range: 172.16.0.0/16
Design Approach: Floor-wise subnet segmentation
Subnet Types Used:
- /25 → Departments (126 hosts)
- /28 → Server Room (14 hosts)
```

---

## 🏢 First Floor Network

| Department        | Network Address | Subnet Mask        | Host Range                  | Broadcast Address |
| ----------------- | --------------- | ------------------ | --------------------------- | ----------------- |
| Sales & Marketing | 172.16.1.0      | 255.255.255.128/25 | 172.16.1.1 – 172.16.1.126   | 172.16.1.127      |
| HR & Logistics    | 172.16.1.128    | 255.255.255.128/25 | 172.16.1.129 – 172.16.1.254 | 172.16.1.255      |

---

## 🏢 Second Floor Network

| Department               | Network Address | Subnet Mask        | Host Range                  | Broadcast Address |
| ------------------------ | --------------- | ------------------ | --------------------------- | ----------------- |
| Finance & Accounts       | 172.16.2.0      | 255.255.255.128/25 | 172.16.2.1 – 172.16.2.126   | 172.16.2.127      |
| Admin & Public Relations | 172.16.2.128    | 255.255.255.128/25 | 172.16.2.129 – 172.16.2.254 | 172.16.2.255      |

---

## 🏢 Third Floor Network

| Department  | Network Address | Subnet Mask        | Host Range                  | Broadcast Address |
| ----------- | --------------- | ------------------ | --------------------------- | ----------------- |
| ICT         | 172.16.3.0      | 255.255.255.128/25 | 172.16.3.1 – 172.16.3.126   | 172.16.3.127      |
| Server Room | 172.16.3.128    | 255.255.255.240/28 | 172.16.3.129 – 172.16.3.142 | 172.16.3.143      |

---

## ⚙️ Network Design Considerations

### 🔹 Subnetting Strategy

* `/25` subnets provide 126 usable IPs per department
* `/28` subnet provides 14 usable IPs for server infrastructure
* Helps in reducing IP wastage and improving efficiency

### 🔹 Segmentation Benefits

* Department isolation improves security
* Reduces broadcast domains
* Easier troubleshooting and management

### 🔹 Scalability

* Additional floors can follow:

  * 172.16.4.0/24
  * 172.16.5.0/24
* Easy to extend without redesigning

---
