# Nmap

[Nmap](https://nmap.org/) (i.e., "Network Mapper") is a powerful open-source network scanning and exploration tool designed to discover hosts, services, and vulnerabilities on a computer network.

Nmap can identify the operating system of a target host as well as versions of services running on open ports based on characteristics of the network responses; information that is valuable for identifying potential vulnerabilities.
Nmap also allows users ability to execute custom scripts to automate tasks, conduct more advanced tests, or perform specific checks (e.g., vulnerability detection). One can also leverage Nmap to launch DOS attacks. 

*Note: It is important to obtain prior authorization before scanning a target network or system.*

<hr>

#### Protocol, Host & Port Specifications 
| Flag | Example | Description |
| - | - | - |
| -sP/-sn | `nmap -sP/-sn <target>` | Ping scan for host discovery only; disable port scanning |
| -sT | `nmap -sT <target>` | TCP connect scan |
| -sA | `nmap -sA <target>` | TCP ACK port scan (Firewall Detection) |
| -sU | `nmap -sU <target>` | UDP port scan |
| -Pn | `nmap -Pn <target>` | Port scan only; disable host discovery |
| -p- | `nmap <target> -p- ` | Port scan all ports |

<br>

#### Service & OS Version Detection
| Flag | Example | Description |
| - | - | - |
| -sV | `nmap -sV <target>` | Service version scan | 
| -O | `sudo nmap -O <target>` | OS detection | 
| -A | `nmap -A <target>` | Aggressive scan; enables OS detection, version detection, script scanning, and traceroute | 

<br>

#### Stealth Mode (Firewall/IDS Evasion & Spoofing)

| Flag | Example | Description |
| - | - | - |
| -sS | `sudo nmap -sS <target>` | TCP SYN scan; does not complete the full TCP three-way handshake |
| -D <ip_address>,<ip_address>| `nmap -D <ip_address>,<ip_address> <target>` | Decoy scan; obfuscates source of nmap scan to help hide source ip address | 
| --spoof-mac <mac_address> | `nmap --spoof-mac <mac_address> <target>` | source MAC address spoofing during nmap scan, to aid in firewall evasion |
| --proxies <proxy_url>,<proxy_url> | `nmap --proxies <proxy_url>,<proxy_url> <target>` | Relay connections through HTTP/SOCKS4 proxies; hides the true source of a scan or evade certain firewall restrictions |
| -f | `nmap -f <target>` | Requested scan (including ping scans) use tiny fragmented IP packets, to aid in firewall/ids evasion
| -n | `nmap -n <target>` | No DNS resolution |

*Note: Decoy scans can be defeated through router path tracing, response-dropping, and other active mechanisms, however it is generally an effective technique for hiding your IP address.*

<br>

#### NSE Scripts
| Flag | Example | Description |
| - | - | - |
| -sC | `nmap -sC <target>` | Performs a script scan using the default set of scripts |
| --script=<script_name> | `nmap --script=<script_name> <target>` | Runs a script scan using the comma-separated list of filenames, script categories, and directories |

<br>
Example Scripts: 

*(See https://nmap.org/nsedoc/scripts/ for full list of custom scripts.)*

| Script | Example | Description | 
| - | - | - |
| whois* |  `nmap --script whois* <target>` | Whois query |
| dns-brute | `nmap -Pn --script dns-brute <target>` | Brute force DNS hostnames guessing subdomains |
| vulners | `nmap -sV --script vulners --script-args mincvss=5.0 <target>` | Crossreferences service versions with CVEs |
| vulnscan | `nmap -sV --script=vulnscan/vulnscan.nse <target>` | Download custom script (https://github.com/scipag/vulscan); Crossreferences service versions with known vulnerabilities | 

<hr> 

#### Example Scripts 

Basic Network Scan: 

```
sudo nmap -sV -O -Pn <target> -p- -v

-sV: Enable version detection, to determine the versions of services running on open ports.

-O: Enable OS detection, to determine version(s) of OS running on server(s).

-Pn: Skip host discovery phase and assumes that the target host is up. It can be useful when host discovery methods are not reliable.

target: IP Address/Domain Name of target system.

-p-: Full port scan; instructs Nmap to scan all 65,535 ports on the target.

-v: verbose; provides detailed information during the scan.
```

Vulnerability Scan:
```
nmap -Pn -sV -sC -vvv -p- <target>

-Pn: Skip host discovery phase and assumes that the target host is up. It can be useful when host discovery methods are not reliable.

-sV: This option enables version detection, attempting to determine the versions of services running on open ports.

-sC: This option enables the default scripts from the Nmap Scripting Engine (NSE), performing a script scan. These scripts can perform various tasks, including service version detection, vulnerability detection, and enumeration.

-vvv Very, very verbose; provides very detailed information during the scan.

-p-: Full port scan; instructs Nmap to scan all 65,535 ports on the target. 

target: IP Address/Domain Name of target system.
```

Brute Force Passwords: 
```
nmap --script brute -Pn <target>
```

DOS Scan & Attack: 
```
nmap --script vuln,dos -Pn <target>

* use -Pn in case the target blocks ping probes.

nmap --max-parallelism 750 -Pn --script http-slowloris --script-args http-slowloris.runforever=true <target>

nmap -T5 -Pn --script http-slowloris --script-args http-slowloris.runforever=true <target>
```
