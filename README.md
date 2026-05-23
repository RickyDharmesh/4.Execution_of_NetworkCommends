# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>
## Program 
client.py
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
server.py
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping:")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```

## Output
<img width="1628" height="353" alt="Screenshot 2026-05-23 195900" src="https://github.com/user-attachments/assets/3c2f5f14-3863-4599-9bc7-88b3eb260d8e" />

NETSTAT:
<img width="1016" height="939" alt="Screenshot 2026-05-23 195105" src="https://github.com/user-attachments/assets/4215ea37-aabb-41fc-9560-62a444539350" />

IPCONFIG:

<img width="1208" height="775" alt="Screenshot 2026-05-23 195913" src="https://github.com/user-attachments/assets/e8c7ae3c-7636-464e-8acd-2abe2b19d754" />


PING:

<img width="1144" height="550" alt="Screenshot 2026-05-23 195923" src="https://github.com/user-attachments/assets/75497da9-6d01-4e7b-99ac-762e38a3a1dd" />


TRACERT:

<img width="1202" height="636" alt="Screenshot 2026-05-23 195926" src="https://github.com/user-attachments/assets/520b4786-d2db-4462-b295-f06fbda38123" />


NSLOOKUP:
<img width="1197" height="821" alt="Screenshot 2026-05-23 195929" src="https://github.com/user-attachments/assets/37cc5a65-462e-4cec-8a84-b0d3ab40bdc9" />



## Result
Thus Execution of Network commands Performed 
