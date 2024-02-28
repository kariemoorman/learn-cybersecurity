## Networking

### Table of Contents
- [OSI Model vs. TCP-IP Model](#osi-model-vs-tcp-ip-model)
- [Network Architecture](#network-architecture)
- [Network Types](#network-types)
- [Network Topology](#network-topology)
- [Network Protocols](#network-protocols)
- [Subnetting](#subnetting)


---
### OSI Model vs. TCP-IP Model

<p align='center'>
<img src="https://github.com/kariemoorman/cybersecurity-toolkit/blob/main/images/osi_tcpip_models.png?raw=true" alt='osi vs. tcp/ip model' style="height:500px;"/></p>


---

### Network Architecture

Computer network architecture defines the physical and logical framework of a computer network. It outlines how computers are organized in the network and what tasks are assigned to those computers. Network architecture components include hardware, software, transmission media (wired or wireless), network topology, and communications protocols.

| Type | Description | 
|-----|----|
| Peer-to-Peer (P2P) | In P2P architecture, two or more computers are connected as “peers,” meaning they have equal power and privileges on the network. A P2P network does not require a central server for coordination. Instead, each computer on the network acts as both a client (a computer that needs to access a service) and a server (a computer that serves the needs of the client accessing a service). Each peer makes some of its resources available to the network, sharing storage, memory, bandwidth, and processing power. |
| Client/Server (Tiered Model) |  In a client/server network, a central server or group of servers manage resources and deliver services to client devices in the network. The clients in the network communicate with other clients through the server. Unlike the P2P model, clients in a client/server architecture don’t share their resources. This architecture type is sometimes called a tiered model because it's designed with multiple levels or tiers. |

---

### Network Types

| Type | Description | Range |
|-----|----|----|
| WAN (wide area network) | AWAN connects computers over a wide area, such as from region to region or even continent to continent. The internet is the largest WAN, connecting billions of computers worldwide. You will typically see collective or distributed ownership models for WAN management. | |
| MAN (metropolitan area network) | A MAN is typically larger than a LAN but smaller than a WAN. Cities and government entities typically own and manage MANs. | |
| CAN (campus area network) | A CAN is larger than a LAN but smaller than a WAN. A CAN serves sites such as colleges, universities, and business campuses. | |
| LAN (local area network) | A LAN connects computers over a relatively short distance, allowing them to share data, files, and resources (e.g., a LAN may connect all the computers in an office building, school, or hospital). Typically, LANs are privately owned and managed. | |
| WLAN (wireless local area network) | WLAN is a LAN, with connections between devices on the network are made wirelessly. | |
| PAN (personal area network) | A PAN serves one person (e.g., a PAN may connect a personal iPhone and a Macbook to share and sync content—text messages, emails, photos, and more—across both devices). | |
| VPN (virtual private network) | A VPN is a secure, point-to-point connection between two network end points. A VPN establishes an encrypted channel that keeps a user’s identity and access credentials, as well as any data transferred. | |


---

### Network Topology

Network topology describes how the nodes and links in a network are arranged. A network node is a device that can send, receive, store, or forward data. A network link connects nodes and may be either cabled or wireless links.

| Type | Description | Advantages | Disadvantages |
|-----|----|----|----|
|Ring | Nodes are connected in a loop, so each device has exactly two neighbors. Adjacent pairs are connected directly; non-adjacent pairs are connected indirectly through multiple nodes. | | |
|Star | All nodes are connected to a single, central hub and each node is indirectly connected through that hub. | | |
|Partial Mesh | Overlapping connections between nodes, such that only some nodes are connected to each other and some are connected to the nodes with which they exchange the most data. | - cost-effective, simpler to execute | - less redundancy |
|Full Mesh | Overlapping connections between nodes, such that every node in the network is connected to every other node. Often reserved for networks that require high redundancy. | - high redundancy, highest level of fault tolerance | - expensive, time consuming to execute |
|Bus | Every network node is directly connected to a main cable. | | |
|Tree | | | |
|Point-to-Point | | | |


---

### Network Protocols



---

### Subnetting
