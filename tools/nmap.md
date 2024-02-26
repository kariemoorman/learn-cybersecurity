# Nmap

[Nmap](https://nmap.org/) (i.e., "Network Mapper") is a powerful open-source network scanning and exploration tool designed to discover hosts, services, and vulnerabilities on a computer network.

Nmap can identify the operating system of a target host as well as versions of services running on open ports based on characteristics of the network responses; information that is valuable for identifying potential vulnerabilities.
Nmap also allows users ability to execute custom scripts to automate tasks, conduct more advanced tests, or perform specific checks (e.g., vulnerability detection).

<hr>

#### Protocol, Host & Port Specifications 
| Flag | Example | Description |
| - | - | - |
| -sP | `nmap -sP <target>` | Ping scan |
| -sT | `nmap -sT <target>` | TCP connect scan |
| -sA | `nmap -sA <target>` | TCP ACK port scan (Firewall Detection) |
| -sU | `nmap -sU <target>` | UDP port scan |
| -sn | `nmap -sn <target>` | Host discovery only; disable port scanning |
| -Pn | `nmap -Pn <target>` | Port scan only; disable host discovery |
| -p- | `nmap <target> -p- ` | Port scan all ports |


#### Service & OS Version Detection
| Flag | Example | Description |
| - | - | - |
| -sV | `nmap -sV <target>` | Service version scan | 
| -O | `sudo nmap -O <target>` | OS detection | 
| -A | `nmap -A <target>` | Aggressive scan; enables OS detection, version detection, script scanning, and traceroute | 


#### Stealth Mode (Firewall/IDS Evasion & Spoofing)

| Flag | Example | Description |
| - | - | - |
| -sS | `sudo nmap -sS <target>` | TCP SYN scan; does not complete the full TCP three-way handshake |
| -D <ip_address>,<ip_address>| `nmap -D <ip_address>,<ip_address> <target>` | Decoy scan; obfuscates source of nmap scan to help hide source ip address | 
| --spoof-mac <mac_address> | `nmap --spoof-mac <mac_address> <target>` | source MAC address spoofing during nmap scan, to aid in firewall evasion |
| --proxies <proxy_url>,<proxy_url> | `nmap --proxies <proxy_url>,<proxy_url> <target>` | Relay connections through HTTP/SOCKS4 proxies; hides the true source of a scan or evade certain firewall restrictions |
| -f | `nmap -f <target>` | Requested scan (including ping scans) use tiny fragmented IP packets, to aid in firewall/ids evasion
| -n | `nmap -n <target>` | No DNS resolution |

Note: Decoy scans can be defeated through router path tracing, response-dropping, and other active mechanisms, however it is generally an effective technique for hiding your IP address.

#### Scripts
| Flag | Example | Description |
| - | - | - |
| -sC | `nmap -sC <target>` | Performs a script scan using the default set of scripts |
| --script=<script_name> | `nmap --script smb* <target>` | Runs a script scan using the comma-separated list of filenames, script categories, and directories |

Example Scripts: 
(See https://nmap.org/nsedoc/scripts/ for full list of custom scripts.)

| Script | Example | Description | 
| - | - | - |
| whois* |  `nmap --script whois* <target>` | Whois query |
| dns-brute | `nmap -Pn --script dns-brute <target>` | Brute force DNS hostnames guessing subdomains |
| vulners | `nmap -sV --script vulners --script-args mincvss=5.0 <target>` | Crossreferences service versions with CVEs |
| vulnscan | `nmap -sV --script=vulnscan/vulnscan.nse <target>` | Download custom script (https://github.com/scipag/vulscan); Crossreferences service versions with known vulnerabilities | 

<hr> 

#### Example Scripts 

```
nmap -Pn -sV -sC -vvv -p- <target>

-Pn: Skip host discovery phase and assumes that the target host is up. It can be useful when host discovery methods are not reliable.

-sV: This option enables version detection, attempting to determine the versions of services running on open ports.

-sC: This option enables the default scripts from the Nmap Scripting Engine (NSE), performing a script scan. These scripts can perform various tasks, including service version detection, vulnerability detection, and enumeration.

-vvv Verbose; provides very detailed information during the scan.

-p-: Full port scan; instructs Nmap to scan all 65,535 ports on the target. 

target: IP Address/Domain Name of target system.
```
