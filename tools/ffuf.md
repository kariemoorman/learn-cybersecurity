# Ffuf
[Ffuf](https://github.com/ffuf/ffuf) ("Fuzz Faster U Fool") is an open-source web application fuzzing tool. Fuzzing is a technique used to discover vulnerabilities or weaknesses in software by providing unexpected or random input to the target application. 
Ffuf is written in Go and is designed to be fast and flexible.

---

### Wordlists:
- [SecLists - Web Content](https://github.com/danielmiessler/SecLists/tree/master/Discovery/Web-Content)
- [SecLists - DNS](https://github.com/danielmiessler/SecLists/tree/master/Discovery/DNS)
- [SecLists - Usernames](https://github.com/danielmiessler/SecLists/tree/master/Usernames)

---

### Examples

#### Subdirectory Enumeration:

```
ffuf -u http://<target_ip_address>/FUZZ -w </path/to/subdirectory_wordlist.txt>

Optional Flags:

-recursion
```

#### Subdomain Enumeration:

```
ffuf -u http://FUZZ.<top-level_domain_name> -w </path/to/subdomain_wordlist.txt>
```

#### Domain & Subdirectory Enumeration:

```
ffuf -u https://FUZZDOMAIN/FUZZDIR -w </path/to/subdirectory_wordlist.txt>:FUZZDIR,<path/to/domain_wordlist.txt>:FUZZDOMAIN
```

#### File Enumeration: 

```
ffuf -u http://<target_ip_address>/FUZZ -w </path/to/subdirectory_wordlist.txt> -e <extension (e.g., .txt)>

Optional:

-mc <status_code (e.g., 200)>
```

#### Username Enumeration: 

```
ffuf -w </path/to/wordlist.txt> -X POST -d "username=FUZZ&&password=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://<top-level_domain_name>/login -mr "username already exists"
```
