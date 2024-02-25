## Hydra 

[Hydra](https://en.kali.tools/?p=220) is a powerful password-cracking tool that is used for various network protocols. 
It is known for its versatility and the ability to perform brute-force attacks, dictionary attacks, and other types of password attacks. 
Hydra supports a wide range of protocols, including HTTP, HTTPS, FTP, SMB, SSH, POP3, Telnet, LDAP, PostgreSQL and MYSQL.

#### HTTP Login Attack:
```
hydra -l <username> -P </path/to/password_wordlist.txt> <target_ip_address> http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V
```

#### SSH Attack: 
```
hydra -l <username> -P </path/to/password_wordlist.txt> <target_ip_address> ssh -s <port_number>
```

#### FTP Attack: 
```
hydra -l <username> -P </path/to/password_wordlist.txt> <target_ip_address> ftp -s <port_number>
```

<hr>

## John the Ripper

[John the Ripper (i.e., "John")](https://www.openwall.com/john/doc) is open-source password cracking software. 
It is designed to identify weak passwords by attempting to crack password hashes through various attack methods. 
John the Ripper is capable of performing dictionary attacks, brute-force attacks, and hybrid attacks against password hashes.

John the Ripper supports various password cracking techniques, including dictionary attacks (using wordlists), brute-force attacks (systematic trial-and-error), and hybrid attacks (combining dictionary and brute-force methods).
John can also crack password hashes from a variety of cryptographic hash functions such as MD5, SHA-1, SHA-256, and SHA-512. 

#### Dictionary Attack:
```
john --wordlist=</path/to/password_wordlist.txt> <hashed_passwords.txt>
```

#### Brute-Force Attack:
```
john --incremental <hashed_passwords.txt>
```

#### Hash Cracking Attack:
```
john --format=<hash_function> <hashed_passwords.txt>
```

#### Hash Cracking Attack in Single Mode (generate password variations):
```
john --single --format=<hash_function> <hashed_password.txt>
```

#### Hash Cracking Attack with Dictionary:
```
john --wordlist=</path/to/password_wordlist.txt> --format=<hash_function> <hashed_passwords.txt>
```

#### Cracking Zip Files:
```
zip2john <filename.zip> > zip.hashes

john zip.hashes
```

### Password Cracking by OS 

#### Windows 

```
john --format=lm <hashed_passwords.txt>
```

#### Linux 

- etc/passwd: stores user information e.g., username, user id, login shell.
- etc/shadow: contains password information, e.g., password hash, password expiration.

```
unshadow /etc/passwd /etc/shadow > output.db

john output.db
```

<hr>

## Hashcat 


