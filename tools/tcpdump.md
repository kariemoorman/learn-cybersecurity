## TCPDump

TCPDump is a command line tool that captures and analyzes network traffic on Nix-based OS for monitoring and troubleshooting. 
TCPDump allows users ability to filter network traffic based on user-specified criteria (e.g., network interface and protocol), 
making it versatile for capturing and analyzing different types of network communication in real-time.

Output pcap files generated using tcpdump can be viewed and inspected using [Wireshark](https://www.wireshark.org/).

---

### Installation

#### Linux
##### Ubuntu, Debian, & Mint
```
sudo apt update && sudo apt install tcpdump
```
##### Arch
```
sudo pacman -S tcpdump
```
##### CentOS
```
sudo yum install tcpdump
```

##### Fedora & RedHat
```
sudo dnf install tcpdump
```

#### MacOS

If not already installed, first install [MacPorts](https://www.macports.org/install.php), then

```
sudo port install tcpdump
```

---

### Basic Commands

For full list of flags, see `man tcpdump`.

Add verbose or very verbose output: 
```
sudo tcpdump  -v
sudo tcpdump -vv
```

Capture a specified number of packets: 
```
sudo tcpdump -c <number>
```

Print a list of all available network interfaces that tcpdump can collect packets from:
```
sudo tcpdump -D
```

Listen to a specific interface:
```
sudo tcpdump -i <network_interface>
```

Display IP addresses instead of domain names:
```
sudo tcpdump -n
```

Capture all traffic from a specific protocol (e.g., port, host, protocol, network range, udp, icmp, arp, tcp): 
```
sudo tcpdump -n < (src | dst) host <IP> | port <number> | portrange <number-number> | proto <number> | net <IP> | udp | icmp > 
```

Print packet in ASCII format:
```
sudo tcpdump -n -A
```

Print packet in HEX format:
```
sudo tcpdump -n -X
```

Capture and save packets to a file: 
```
sudo tcpdump -w <FILENAME>.pcap
```

Inspect contents of pcap file:
```
sudo tcpdump -r data.pcap
```
