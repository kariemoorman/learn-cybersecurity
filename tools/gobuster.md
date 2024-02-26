# Gobuster


[Gobuster](https://github.com/OJ/gobuster) is an open-source tool designed for scanning web applications and websites to identify and locate hidden files and directories.
Gobuster performs directory and file brute-forcing by sending HTTP requests to a target server and analyzing the responses.
It is commonly used for web application penetration testing and vulnerability assessment. 

<hr>

### Table of Contents
- [Wordlists](#wordlists)
- [Example Commands](#example-commands)

<hr>

### Wordlists

- [Wordlists](https://github.com/kkrypt0nn/wordlists/tree/main/wordlists)
- [DNS Wordlist](https://github.com/Azathothas/Wordlists)
- [AWS S3 Wordlist](https://github.com/koaj/aws-s3-bucket-wordlist)

<hr>

### Example Commands

#### Subdirectory Enumeration:

Directory brute-forcing mode to discover hidden folders and files.

```
gobuster dir -u <target> -w </path/to/directory_wordlist.txt>

gobuster dir -u <target>/login -c ‘username=^USER^&password=^PASS^’ -t 50 -w </path/to/password_list.txt>


Example Output:

<target>/login
<target>/categories
<target>/admin
<target>/index
<target>/download
```


#### DNS Subdomain Enumeration:

DNS subdomain brute-forcing mode.

```
gobuster dns -d <target> -w </path/to/subdomain_wordlist.txt>

Example Output:
music.<target>
news.<target>
local.<target>
admin.<target>
```

#### Vhost Enumeration:

Virtual host brute-forcing mode.

```
gobuster vhost -u <target> -w </path/to/vhost_wordlist.txt>

Example Output:
mail.<target>
apache.<target>
```

#### S3 Enumeration:

Enumerate open S3 buckets and look for existence and bucket listings.

```
gobuster s3 -w <s3_bucket_wordlist.txt>

Example Output:

http://prod_test.s3.amazonaws.com/
http://test-images.s3.amazonaws.com/
```


#### Fuzzing:

```
gobuster fuzz -u <target>/FUZZ -w <fuzz_wordlist>.txt

Example Output:

<target>/php.ini
<target>/.gitignore
<target>/phpinfo.php
<target>/docs
<target>/external
<target>/config
```


#### Additional Flags:

| Flag | Mode | Description | 
| - | - | - |
| -c | DIR, VHOST | Cookies to use for the requests |
| -a | DIR, VHOST | Set the User-Agent string (default "gobuster/3.1.0") |
| -U | DIR, VHOST | Username for Basic Auth |
| -P | DIR, VHOST | Password for Basic Auth |
| -p | DIR, VHOST | Proxy to use for requests [http(s)://host:port] |
| -c | DNS | Show CNAME records |
| -i | Global | Show IP addresses |
| -t  < integer > | Global | Number of concurrent threads (default 10) |
| -o <output_file.txt> | Global | Specify name of output file |
