# Networking Fundamentals — 01: Understanding Local Area Networking

> Notes from Microsoft Learn — Networking Fundamentals  
> Part of my cybersecurity learning roadmap.

---

## Table of Contents

1. [Core Concepts](#1-core-concepts)
2. [Network Devices](#2-network-devices)
3. [Addressing](#3-addressing)
4. [Network Media & Data Transfer](#4-network-media--data-transfer)
5. [Network Topologies](#5-network-topologies)
6. [Network Standards — Ethernet](#6-network-standards--ethernet)
7. [Network Models](#7-network-models)
8. [Network Segmentation](#8-network-segmentation)
9. [Network Documentation](#9-network-documentation)

---

## 1. Core Concepts

| Term | Definition |
|------|-----------|
| **Data** | A unit of information that flows across a network. |
| **Node** | Any end device on a network. |
| **Client** | A device that requests services. |
| **Server** | A device that fulfills service requests. |
| **Peer** | A device that can act as both client and server. Most devices behave as peers. |
| **Bandwidth** | The maximum amount of data that can be transferred across a network at a given time. |
| **Transport Protocol** | A set of rules and standards that govern how data is transported, enabling different devices to interconnect and communicate. |

### Local Area Network (LAN)

A **LAN** is a group of computers and devices confined to a small geographic area (such as a single building) that share a common communication medium — wired, wireless, or both.

All devices in a LAN share the same **network ID** (see [Addressing](#3-addressing)). To communicate with a device on a *different* network, a router is required.

Networks are used to **exchange data**, share information, communicate, and organize resources.

---

## 2. Network Devices

### Network Adapter (NIC)
A **Network Interface Card** is the hardware component that allows a device to send and receive data on a network. Wired NICs typically feature an **RJ-45 jack**. Every NIC is assigned a unique MAC address.

---

### Hub
A hub is the most basic central connecting device. When a device sends data to a hub, the hub **broadcasts** that data to *all* connected devices. Devices that the data wasn't intended for simply ignore it.

**Bandwidth caveat:** A hub's bandwidth is *shared* across all ports. For example, a 100 Mbps hub splits that bandwidth among all active transfers happening simultaneously.

---

### Switch
A switch is a smarter version of a hub. It keeps track of the **MAC addresses** of devices connected to each of its ports. When data arrives, the switch reads the destination MAC address in the frame header and forwards it *only* to the correct port — not to everyone.

**Bandwidth advantage:** Because traffic is directed, the full specified bandwidth is available on *every port* simultaneously, unlike a hub.

---

### Router
A router connects **multiple networks** together, enabling devices on different networks to communicate with each other. To send data outside your LAN, it must pass through a router.

---

### Firewall
A firewall is essentially a **router with enhanced security functionality**. It interconnects two networks while applying security rules that standard routers do not offer. The depth of security depends on the specific firewall.

---

### Wireless Access Point (WAP)
A WAP allows wireless devices to connect to a **wired network**. The backbone of most networks is wired, and WAPs serve as the bridge between wireless clients and that wired infrastructure.

---

## 3. Addressing

### MAC Address (Media Access Control)
A **MAC address** is a unique identifier assigned to the physical network port of a NIC. Every device with a network card has one. MAC addresses operate at **Layer 2** of the OSI model and are used by switches to direct traffic within a LAN.

### IP Address
An **IP address** uniquely identifies a device and its associated network, enabling devices to send and receive data across networks. IP addresses are associated with MAC addresses via the **TCP/IP protocol**.

Every IP address has two components:

| Component | Purpose | Example (`192.168.1.5`) |
|-----------|---------|------------------------|
| **Network ID** | Identifies the network | `192.168.1` |
| **Host ID** | Identifies the specific device | `.5` |

Devices sharing the same network ID are on the same LAN and can communicate directly via a hub or switch. Communication across different network IDs requires a **router**.

---

## 4. Network Media & Data Transfer

### Media
**Media** is the physical or wireless medium over which data travels. Common types include:

- **Copper twisted-pair cables** (most common for wired LANs)
- **Wireless (radio frequency)**
- **Fiber optic**

### Serial Data Transfer
On network cables, data travels **one bit at a time** in a single bit stream — this is called **serial data transfer**.

### Data Transfer Rate
The **Data Transfer Rate** defines the maximum number of bits per second (bps) that can be transmitted over a network.

> **Important distinction:**  
> - Network speeds use a **lowercase b** → **Mbps** (megabits per second)  
> - Storage sizes use an **uppercase B** → **MB** (megabytes)  
> - 1 byte = 8 bits

### Types of Transmission

| Type | Description | Analogy |
|------|-------------|---------|
| **Broadcast** | Data sent to all devices | Radio |
| **Unicast** | Data sent to one specific device | Walkie-talkie |

---

## 5. Network Topologies

A **network topology** defines how devices (hosts) are physically or logically connected in a network.

| Topology | Description | Notes |
|----------|-------------|-------|
| **Bus** | Devices connected in a line | If one segment fails, everything after it goes down |
| **Ring** | Closed loop; each device connects to two others | More logical than physical; used by Token Ring and **FDDI** (Fiber Distributed Data Interface) |
| **Star** | All devices connect to a central hub or switch | **Most common topology** |
| **Mesh** | Every device connects to every other device | Very expensive; highly redundant |
| **Tree** | Hierarchical combination of star topologies | Not very common |

### Star Topology (Most Common)
The center of a star network is typically a **hub, switch, or SOHO router**. Each device connects directly to it via twisted-pair cable. This is the topology you'll encounter most in real environments.

### Token Ring
Devices are connected to a central device called a **Multistation Access Unit (MAU/MSAU)**. Physically resembles a star, but data travels logically in a ring.

---

## 6. Network Standards — Ethernet

**Ethernet** is the IEEE **802.3** standard that defines how data is sent and received between network adapters, hubs, switches, and other devices. It is the most widely installed LAN technology.

### Common Ethernet Standards

| Standard | Name | Speed |
|----------|------|-------|
| **802.3u** | Fast Ethernet | 100 Mbps |
| **802.3ab** | Gigabit Ethernet | 1,000 Mbps (1 Gbps) |

### Frames
On Ethernet networks, data is transmitted in **frames** — sequences of bits with a detectable beginning and end. A frame is a **Layer 2** (Data Link) construct in the OSI model that wraps a data packet for transmission on the physical network.

---

## 7. Network Models

### Centralized Computing
All processing happens at a central location. Users interact via **terminals** connected to the main system. This model has seen a modern revival through:

- **Remote Desktop Services** — users connect remotely to a central machine
- **Thin clients** — devices with no local hard drive; they load their OS from RAM and rely on a central server for all applications and data. This makes thin clients a *hybrid* of centralized and distributed computing — the processing is centralized, but the device itself is still a distinct endpoint

### Client/Server Model
The dominant model for most enterprise networks. Responsibilities are clearly separated:

- **Server** — provides centralized services. Common server roles include: file, print, database, network controller, messaging/email, and web. Example: Windows Server
- **Client** — requests and consumes those services. Example: Windows workstation

### Peer-to-Peer (P2P)
Every device has its own processing power and can act as both client and server. P2P is common in:

- Small home or office networks
- File-sharing networks (e.g., Napster, Gnutella, G2)
- Applications like Skype, VoIP, and cloud services

### Distributed Computing
Encompasses both client/server and P2P models. Every workstation has its own processing power, but resources and services can still be shared across the network.

---

## 8. Network Segmentation

### Virtual LAN (VLAN)
A **VLAN** is a logical grouping of devices on a switch that communicate as if they were on the same physical network, **regardless of their physical location**.

- Managed at the switch level
- Commonly used to separate departments within a company (e.g., HR, Finance, IT) without needing separate physical switches
- Provides improved security and reduced broadcast traffic
- Routers can also segment networks, but they are more expensive; VLANs are a cost-effective alternative

---

## 9. Network Documentation

Network documentation describes the **physical and logical** methods used to connect devices. It is created:

- Before a network is built
- When changes are made to an existing network

A well-documented network makes troubleshooting, auditing, and expansion significantly easier.

**Tool:** Microsoft Visio is commonly used for network diagrams and documentation.

---

*These notes are part of my cybersecurity learning journey. See the full roadmap in the repository README.*
