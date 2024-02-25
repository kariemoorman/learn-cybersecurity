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

#### Password Cracking by OS 

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

[Hashcat](https://hashcat.net/hashcat/) is an open-source password recovery tool that is used for recovering lost or forgotten passwords. It is known for its speed and versatility in cracking password hashes using a variety of attack modes and techniques. Hashcat supports CPU and GPU acceleration, making it one of the fastest password-cracking tools available.

Hashcat offers various attack modes, including dictionary attacks, brute-force attacks, hybrid attacks (combination of dictionary and brute-force), rule-based attacks, and mask attacks. 
Hashcat supports a wide range of password hashing algorithms, including MD5, SHA-1, SHA-256, SHA-512, and NTLM.

#### Dictionary Attack:
```
hashcat -m <hash_mode> -a 0 -o <output_file.txt> <hash_file.txt> <password_wordlist.txt>

-m <hash_mode>: Replace this with the appropriate hash mode identifier (e.g., 0 for MD5).
-a 0: Specifies the attack mode for a dictionary attack.
-o output_file.txt: Outputs the cracked passwords to a file.
hash_file.txt: The file containing the hashed passwords.
password_wordlist.txt: The dictionary file.
```

#### Combinator Attack: 
```
hashcat -m <hash_mode> -a 1 -o <output_file.txt> <hash_file.txt> <password_list1.txt> <password_list2.txt>

-m <hash_mode>: Replace this with the appropriate hash mode identifier.
-a 1: Specifies the attack mode as combinator attack.
-o output_file.txt: Outputs the cracked passwords to a file.
hash_file.txt: The file containing the hashed passwords.
password_list1.txt and password_list2.txt: Two separate wordlists you want to combine.
```

#### Brute-Force Attack:
```
hashcat -m <hash_mode> -a 3 -o <output_file.txt> <hash_file.txt> ?a?a?a?a?a?a

-m <hash_mode>: Replace this with the appropriate hash mode identifier.
-a 3: Specifies the attack mode for a brute-force attack.
-o output_file.txt: Outputs the cracked passwords to a file.
hash_file.txt: The file containing the hashed passwords.
?a?a?a?a?a?a: Represents the mask for a six-character brute-force attack.
```

#### Hybrid Attack (Combination of Dictionary and Brute-Force):
```
hashcat -m <hash_mode> -a 6 -o <output_file.txt> <hash_file.txt> <password_list.txt> ?d?d?d?d?d

-m <hash_mode>: Replace this with the appropriate hash mode identifier.
-a 6: Specifies the attack mode for a hybrid attack.
-o output_file.txt: Outputs the cracked passwords to a file.
hash_file.txt: The file containing the hashed passwords.
password_list.txt: The dictionary file.
?d?d?d?d?d: Represents the mask for a five-digit brute-force attack.
```

#### Rule-Based Attack:
```
hashcat -m <hash_mode> -a 0 -o <output_file.txt> --rules-file <rules.txt> <hash_file.txt> <password_list.txt>

-m <hash_mode>: Replace this with the appropriate hash mode identifier.
-a 0: Specifies the attack mode for a dictionary attack.
-o output_file.txt: Outputs the cracked passwords to a file.
--rules-file rules.txt: Specifies the file containing custom rules.
hash_file.txt: The file containing the hashed passwords.
password_list.txt: The dictionary file.
```

#### Mask Attack:
```
hashcat -m <hash_mode> -a 3 -o <output_file.txt> <hash_file.txt> ?l?l?l?l?d?d?d?d

-m <hash_mode>: Replace this with the appropriate hash mode identifier.
-a 3: Specifies the attack mode for a brute-force attack.
-o output_file.txt: Outputs the cracked passwords to a file.
hash_file.txt: The file containing the hashed passwords.
?l?l?l?l?d?d?d?d: Represents the mask for a four-character lowercase letters followed by four digits.
```

