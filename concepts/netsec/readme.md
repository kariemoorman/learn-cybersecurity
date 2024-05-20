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


--- 

### Network Types

--- 

### Network Typology


  

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

<h3 align='center'>OSI Model & Attack Vectors</h3>
<p align='center'><img src='https://github.com/kariemoorman/learn-cybersecurity/blob/main/images/osi_v_attacks.png' height="500"> </p>


<h3 align='center'>OSI vs. TCP/IP Models</h3>

<p align='center'><img src='https://github.com/kariemoorman/learn-cybersecurity/blob/main/images/osi_v_tcpip.png' height="500"></p>


---

### Subnetting

Subnetting is the process of taking a large block of IP addresses and turning it into a bunch of smaller blocks of IP addresses. 

Benefits of Subnetting: 

- Smaller networks are more efficient. The less addresses there are, the less devices there will be on the network. The less devices there are, the less broadcasts that can happen.

- Smaller networks allow for segmentation of a specific set of devices to that network. This makes managing the network and network devices, e.g., firewalls, much easier.

- Subnetting allows for more efficient use of IPv4 addresses. With subnetting it is possible to carve out space necessary for only a set of target devices, reducing IP address waste.
