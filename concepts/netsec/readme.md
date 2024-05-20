# Network Security

## Table of Contents
- [Network Architecture](#network-architecture)
- [Network Types](#network-types)
- [Network Typology](#network-typology)
- [Network Protocols](#network-protocols)
- [OSI Model](#osi-model)
- [Subnetting](#subnetting)



--- 

### Network Architecture

Computer network architecture defines the physical and logical framework of a computer network. It outlines how computers are organized in the network and what tasks are assigned to those computers. Network architecture components include hardware, software, transmission media (wired or wireless), network topology, and communications protocols.

| Type | Description | 
|-----|----|
| <p align='center'><img src='https://cdn3.iconfinder.com/data/icons/cryptocurrency-188/32/Cryptocurrency_interact_peer-to-peer_p2p_persons-512.png' alt='p2p' width="75px;" height="75px;" style="max-width:100%"><br> Peer-to-Peer (P2P)</p> | In P2P architecture, two or more computers are connected as “peers,” meaning they have equal power and privileges on the network. A P2P network does not require a central server for coordination. Instead, each computer on the network acts as both a client (a computer that needs to access a service) and a server (a computer that serves the needs of the client accessing a service). Each peer makes some of its resources available to the network, sharing storage, memory, bandwidth, and processing power. |
| <p align='center'><img src='https://cdn.iconscout.com/icon/premium/png-256-thumb/client-server-32-1058806.png' alt='client-server' width="75px;" height="75px;" style="max-width:100%"><br> Client/Server (Tiered Model)</p> |  In a client/server network, a central server or group of servers manage resources and deliver services to client devices in the network. The clients in the network communicate with other clients through the server. Unlike the P2P model, clients in a client/server architecture don’t share their resources. This architecture type is sometimes called a tiered model because it's designed with multiple levels or tiers. |

--- 

### Network Types

| Type | Description | Range |
|-----|----|----|
| WAN (wide area network) | AWAN connects computers over a wide area, such as from region to region or even continent to continent. The internet is the largest WAN, connecting billions of computers worldwide. You will typically see collective or distributed ownership models for WAN management. | Intercontinental or global, spanning thousands to tens of thousands of miles. Global scale, spanning across regions, countries, or continents. |
| MAN (metropolitan area network) | A MAN is typically larger than a LAN but smaller than a WAN. Cities and government entities typically own and manage MANs. | Typically covers tens to hundreds of miles. Extends across a city or metropolitan area. |
| CAN (campus area network) | A CAN is larger than a LAN but smaller than a WAN. A CAN serves sites such as colleges, universities, and business campuses. | Usually covers a few miles. Covers a campus or a group of buildings within a close proximity, such as a university campus or a business complex. |
| LAN (local area network) | A LAN connects computers over a relatively short distance, allowing them to share data, files, and resources (e.g., a LAN may connect all the computers in an office building, school, or hospital). Typically, LANs are privately owned and managed. | Typically covers a few hundred meters to a few kilometers. Limited a relatively small geographical area, such as a single building, office floor, or home. |
| WLAN (wireless local area network) | WLAN is a LAN, with connections between devices on the network are made wirelessly. | Similar to LAN, covering a few hundred meters to a few kilometers. Connections between devices are made wirelessly within a limited area, typically covering a building or a specific area within a building. |
| PAN (personal area network) | A PAN serves one person (e.g., a PAN may connect a personal iPhone and a Macbook to share and sync content—text messages, emails, photos, and more—across both devices). | Very short range, usually within a few meters. Covers the immediate vicinity of an individual, such as a person's workspace or personal devices in close proximity. |
| VPN (virtual private network) | A VPN is a secure, point-to-point connection between two network end points. A VPN establishes an encrypted channel that keeps a user’s identity and access credentials, as well as any data transferred. | Virtual, as it operates over existing networks (like the internet) but can provide secure connections over long distances, effectively extending the range of a private network. |

--- 

### Network Typology

Network topology describes how the nodes and links in a network are arranged. A network node is a device that can send, receive, store, or forward data. A network link connects nodes and may be either cabled or wireless links.

| Type | Description | Advantages | Disadvantages |
|-----|----|----|----|
|Ring | Nodes are connected in a loop, so each device has exactly two neighbors. Adjacent pairs are connected directly; non-adjacent pairs are connected indirectly through multiple nodes. | - Simple to implement <br> - Equal traffic distribution <br> - No central point of failure | - If one node or link fails, the entire network can be affected <br> - Limited scalability |
|Star | All nodes are connected to a single, central hub and each node is indirectly connected through that hub. | - Centralized control <br> - Easy to add or remove devices <br> - Fault isolation | - Dependency on central hub <br> - Failure of central hub disrupts entire network <br> - Limited scalability |
|Partial Mesh | Overlapping connections between nodes, such that only some nodes are connected to each other and some are connected to the nodes with which they exchange the most data. | - Cost-effective <br> - Simpler to execute | - Less redundancy |
|Full Mesh | Overlapping connections between nodes, such that every node in the network is connected to every other node. Often reserved for networks that require high redundancy. | - High redundancy, highest level of fault tolerance | - Expensive <br> - Time consuming to execute |
|Bus | Every network node is directly connected to a main cable. | - Simple to implement <br> - Cost-effective for small networks <br> - Easy to expand | - Single point of failure (the main cable) <br> - Limited scalability <br> - Performance degradation with additional nodes |
|Tree | Nodes are arranged hierarchically, with a root node at the top and branches extending downward. | - Scalable <br> - Hierarchical structure simplifies network management | - Dependency on root node <br> - Limited fault tolerance <br> - Adding or removing nodes can disrupt entire branches |
|Point-to-Point | Direct connection between two nodes, often used in telecommunications and networking. | - Simplest topology <br> - Low latency <br> - Secure communication | - Limited scalability <br> - Each connection requires dedicated resources <br> - Difficult to manage in large networks |
  

----

### Network Protocols

#### TCP vs. UDP

<table>
  <th width='50%;'>TCP</th>
  <th>UDP</th>
    <tr>
    <td align='center'><img src='https://github.com/kariemoorman/learn-networking/blob/main/images/tcp_provider.png' alt='tcp' /></td>
    <td align='center'><img src='https://github.com/kariemoorman/learn-networking/blob/main/images/udp_provider.png' alt='udp' /></td>
  </tr>
  <tr>
    <td valign="top">Reliable Delivery</td>
    <td valign="top">Unreliable Delivery</td>
  </tr>
  <tr>
    <td valign="top">Error Checking</td>
    <td valign="top">No Error Checking</td>
  </tr>
  <tr>
    <td valign="top">Flow Control</td>
    <td valign="top">No Flow Control</td>
  </tr>
  <tr>
    <td valign="top">Congestion Control</td>
    <td valign="top">No Congestion Control</td>
  </tr>
  <tr>
    <td valign="top">Ordered Delivery<ul><li>In a TCP session, data packets can be sent in different orders. TCP can reorder the packets at the receiving end.</li></ul></td>
    <td valign="top">No Ordered Delivery<ul><li>UDP has no reordering mechanism.</li></ul></td>
  </tr>
  <tr>
    <td valign="top">Connection Establishment</td>
    <td valign="top">No Connection Establishment</td>
  </tr>
</table>


--- 

### OSI Model

<h3 align='center'>OSI vs. TCP/IP Models</h3>
<p align='center'><img src='https://github.com/kariemoorman/learn-cybersecurity/blob/main/images/osi_v_tcp-ip.png' height="500"></p>


<h3 align='center'>OSI Model & Attack Vectors</h3>
<p align='center'><img src='https://github.com/kariemoorman/learn-cybersecurity/blob/main/images/osi_v_attacks.png' height="500"> </p>


---

### Subnetting

Subnetting is the process of taking a large block of IP addresses and turning it into a bunch of smaller blocks of IP addresses (see [IP-Subnet-Calculator](https://github.com/kariemoorman/ip-subnet-calculator)). 

<b>How Subnetting Works:</b> 

- IP Addressing: In computer networks, devices are identified using IP addresses. IPv4 addresses, for instance, consist of 32 bits, often represented as four octets separated by periods (e.g., 192.168.1.1).

- Subnet Mask: A subnet mask is a 32-bit number used to distinguish the network portion of an IP address from the host portion. It consists of a series of ones followed by a series of zeros. For example, the subnet mask 255.255.255.0 means that the first 24 bits (or the first three octets) are dedicated to identifying the network, leaving the last octet for addressing hosts within that network.

- Dividing Networks: By customizing the subnet mask, you can divide a network into smaller segments. For instance, if you have a network with the IP range 192.168.1.0 - 192.168.1.255 and you use a subnet mask of 255.255.255.0, you effectively have one subnet with 254 available host addresses (the first and last addresses are reserved for network address and broadcast address, respectively). However, if you subnet further, say into two subnets, each would have half the number of available host addresses.

<b>Benefits of Subnetting:</b> 

- Smaller networks are more efficient. The less addresses there are, the less devices there will be on the network. The less devices there are, the less broadcasts that can happen.

- Smaller networks allow for segmentation of a specific set of devices to that network. This makes managing the network and network devices, e.g., firewalls, much easier.

- Subnetting allows for more efficient use of IPv4 addresses. With subnetting it is possible to carve out space necessary for only a set of target devices, reducing IP address waste.

---
