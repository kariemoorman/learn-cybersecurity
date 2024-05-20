# Network Security

## Table of Contents
- [OSI Model](#osi-model)
- [Network Typology](#network-typology)
- [Network Protocols](#network-protocols)


--- 

### OSI Model

<h3 align='center'>OSI Model & Attack Vectors</h3>
<p align='center'><img src='https://github.com/kariemoorman/learn-cybersecurity/blob/main/images/osi_v_attacks.png' height="500"> </p>


<h3 align='center'>OSI vs. TCP/IP Models</h3>

<p align='center'><img src='https://github.com/kariemoorman/learn-cybersecurity/blob/main/images/osi_v_tcpip.png' height="500"></p>


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
