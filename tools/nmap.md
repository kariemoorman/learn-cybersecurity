# Nmap

[Nmap](https://nmap.org/) (i.e., "Network Mapper") is a powerful open-source network scanning and exploration tool designed to discover hosts, services, and vulnerabilities on a computer network.

Nmap can identify the operating system of a target host as well as versions of services running on open ports based on characteristics of the network responses; information that is valuable for identifying potential vulnerabilities.
Nmap also allows users ability to execute custom scripts to automate tasks, conduct more advanced tests, or perform specific checks (e.g., vulnerability detection).

<hr>

#### Protocol, Host & Port Specifications 
| Flag | Example | Description |
| - | - | - |
| -sP | `nmap -sP <target_ip_address>` | Ping scan |
| -sA | `nmap -sA <target_ip_address>` | TCP ACK port scan (Firewall Detection) |
| -sU | `nmap -sU <target_ip_address>` | UDP port scan |
| -sn | `nmap -sn <target_ip_address>` | Host discovery only; disable port scanning |
| -Pn | `nmap -Pn <target_ip_address>` | Port scan only; disable host discovery |
| -p- | `nmap <target_ip_address> -p- ` | Port scan all ports |


#### Service & OS Version Detection
| Flag | Example | Description |
| - | - | - |
| -sV | `nmap -sV <target_ip_address>` | Service version scan | 
| -O | `sudo nmap -O <target_ip_address>` | OS detection | 
| -A | `nmap -A <target_ip_address>` | Aggressive scan; enables OS detection, version detection, script scanning, and traceroute | 


#### Stealth Mode (Firewall/IDS Evasion & Spoofing)

| Flag | Example | Description |
| - | - | - |
| -sS | `sudo nmap -sS <target_ip_address>` | TCP SYN scan; does not complete the full TCP three-way handshake |
| -D <ip_address>,<ip_address>| `nmap -D <ip_address>,<ip_address> <target_ip_address>` | Decoy scan; obfuscates source of nmap scan to help hide source ip address | 
| --spoof-mac <mac_address> | `nmap --spoof-mac <mac_address> <target_ip_address>` | source MAC address spoofing during nmap scan, to aid in firewall evasion |
| --proxies <proxy_url>,<proxy_url> | `nmap --proxies <proxy_url>,<proxy_url> <target_ip_address>` | Relay connections through HTTP/SOCKS4 proxies; hides the true source of a scan or evade certain firewall restrictions |
| -f | `nmap -f <target_ip_address>` | Requested scan (including ping scans) use tiny fragmented IP packets, to aid in firewall/ids evasion
| -n | `nmap -n <target_ip_address>` | No DNS resolution |

Note: Decoy scans can be defeated through router path tracing, response-dropping, and other active mechanisms, however it is generally an effective technique for hiding your IP address.

#### Scripts
| Flag | Example | Description |
| - | - | - |
| -sC | `nmap -sC <target_ip_address>` | Performs a script scan using the default set of scripts |
| --script=<script_name> | `nmap --script smb* <target_ip_address>` | Runs a script scan using the comma-separated list of filenames, script categories, and directories |

Example Scripts: 
(See https://nmap.org/nsedoc/scripts/ for full list of custom scripts.)

| Script | Example | Description | 
| - | - | - |
| whois* |  `nmap --script whois* <target_ip_address>` | Whois query |
| dns-brute | `nmap -Pn --script dns-brute <target_ip_address>` | Brute force DNS hostnames guessing subdomains |
| vulners | `nmap -sV --script vulners --script-args mincvss=5.0 <target_ip_address>` | Crossreferences service versions with CVEs |
| vulnscan | `nmap -sV --script=vulnscan/vulnscan.nse <target_ip_address>` | Download custom script (https://github.com/scipag/vulscan); Crossreferences service versions with known vulnerabilities | 

<hr> 

#### Example Scripts 

```
nmap -Pn -sV -sC -vvv -p- <target_ip_address>

-Pn: Skip host discovery phase and assumes that the target host is up. It can be useful when host discovery methods are not reliable.

-sV: This option enables version detection, attempting to determine the versions of services running on open ports.

-sC: This option enables the default scripts from the Nmap Scripting Engine (NSE), performing a script scan. These scripts can perform various tasks, including service version detection, vulnerability detection, and enumeration.

-vvv Verbose; provides very detailed information during the scan.

-p-: Full port scan; instructs Nmap to scan all 65,535 ports on the target. 

ip_address: IP address of target system.
```
