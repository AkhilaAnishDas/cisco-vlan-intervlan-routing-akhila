# Cisco VLAN & Inter-VLAN Routing Lab

## 📌 Overview

This project demonstrates the configuration and implementation of a **VLAN-based network** using **Cisco Packet Tracer**.

The lab includes multiple VLANs, trunk links between switches, inter-VLAN routing using a Layer 3 Core Switch, static IP addressing, and network connectivity testing.

--

## 🎯 Objectives

* Create and configure multiple VLANs.
* Assign switch ports to appropriate VLANs.
* Configure trunk links using **802.1Q**.
* Configure **Native VLAN 999** on trunk links.
* Configure Switch Virtual Interfaces (SVIs) for inter-VLAN routing.
* Enable IP routing on the Core Switch.
* Assign static IP addresses to end devices.
* Configure default gateways.
* Verify connectivity using `ping`.
* Troubleshoot VLAN, trunk, and connectivity issues.

--

## 🏗️ Network Topology

The network consists of:

* Core Layer 3 Switch
* Ground Floor Switch
* Floor 1 Switch
* Floor 2 Switch
* Edge Router
* End devices/PCs

The Core Switch provides **inter-VLAN routing** through SVIs and connects the different floor switches using trunk links.

## 🧩 VLAN Configuration

| VLAN | Purpose               | Default Gateway |
| ---- | --------------------- | --------------- |
| 10   | VLAN 10               | `10.10.10.1`    |
| 20   | VLAN 20               | `10.10.20.1`    |
| 30   | VLAN 30               | `10.10.30.1`    |
| 40   | VLAN 40               | `10.10.40.1`    |
| 50   | VLAN 50               | `10.10.50.1`    |
| 60   | VLAN 60               | `10.10.60.1`    |
| 70   | VLAN 70               | `10.10.70.1`    |
| 99   | Management/Other VLAN | `10.10.99.1`    |
| 999  | Native VLAN           | No IP address   |

--

## 🔗 Trunk Configuration

Trunk links were configured using **IEEE 802.1Q**.

The native VLAN used for trunk connections is:

```text
Native VLAN: 999
Encapsulation: 802.1Q
```

The trunk links were verified using:

```bash
show interfaces trunk
```

The output was checked to ensure that the interfaces were operating in **trunking** mode and using the correct native VLAN.

--

## 🌐 Inter-VLAN Routing

The Core Switch was configured as a Layer 3 switch with IP routing enabled:

```bash
ip routing
```

SVIs were configured for the required VLANs. Each SVI acts as the **default gateway** for devices belonging to that VLAN.

Example:

```bash
interface Vlan10
 ip address 10.10.10.1 255.255.255.224
```
--

## 💻 Static IP Addressing

End devices were configured with static IP addresses.

Each PC was assigned:

* A unique IP address
* The appropriate subnet mask
* The corresponding VLAN gateway

Example:

```text
IP Address:       10.10.10.2
Subnet Mask:      255.255.255.224
Default Gateway:  10.10.10.1
```
--

## 🔍 Verification & Troubleshooting

The following commands were used to verify the configuration:

```bash
show vlan brief
```

```bash
show interfaces trunk
```

```bash
show ip interface brief
```

```bash
show running-config
```

Connectivity was tested using:

```bash
ping <destination-ip>
```

During troubleshooting, issues such as **native VLAN mismatches**, incorrect trunk configuration, and VLAN assignment problems were identified and corrected.

--

## ✅ Expected Results

The completed network should demonstrate:

* VLANs operating correctly.
* Trunk links functioning with 802.1Q.
* Native VLAN 999 configured consistently on trunk links.
* SVIs in an `up/up` state.
* Correct static IP addressing on PCs.
* Successful communication with the appropriate default gateway.
* Successful inter-VLAN communication where permitted.

--

## 📁 Project Files

```text
├── README.md
└── Cisco_VLAN_InterVLAN_Routing.pkt
```
--

## 🛠️ Tools Used

* **Cisco Packet Tracer**
* Cisco IOS CLI
* GitHub

--

## 📚 Key Learning Outcomes

This lab provided practical experience with:

* VLAN creation and management
* Access and trunk ports
* IEEE 802.1Q trunking
* Native VLAN configuration
* Layer 3 switching
* Inter-VLAN routing
* Static IP configuration
* Network troubleshooting
* Connectivity verification using `ping`

--

## 📸 Screenshots

### 1. Network Topology

![Network Topology](screenshots/topology.png)

### 2. VLAN Configuration

![VLAN Configuration](screenshots/vlan-configuration.png)

### 3. Trunk Configuration

![Trunk Configuration](screenshots/trunk-configuration.png)

### 4. IP Interface Configuration

![IP Interface Configuration](screenshots/ip-interface.png)

### 5. Connectivity Testing

![Connectivity Test](screenshots/ping-test.png)

--

## 👤 Author

**Akhila Anish Das** <BR>
**Roll no: 150096725016** <BR>
**Batch: Larry Page** <BR>
**Course: BTECH CSE 2025-29** <BR>
**Faculty: Dr. Dipanjan Biswas** <br>
**Subject: Computer Networking Fundamentals and cyber Security**

---

⭐ *Cisco Networking Lab — VLAN & Inter-VLAN Routing*
