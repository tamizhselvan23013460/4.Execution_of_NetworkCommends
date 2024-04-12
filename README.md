# 4.Execution_of_NetworkCommands
## AIM :
Use of Network commands in Real Time environment
## Software :
Command Prompt And Network Protocol Analyzer
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
### Ping command
### Client.py
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
### Server.py
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### TRACEROUTE COMMAND
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

## Output
### client.py
<img width="740" alt="4 client ouput" src="https://github.com/Ganesh23013987/4.Execution_of_NetworkCommends/assets/147473768/7699b863-f7f5-4b9f-9db7-7a3511f19a52">

### Server.py
<img width="740" alt="4 server output" src="https://github.com/Ganesh23013987/4.Execution_of_NetworkCommends/assets/147473768/5e5b83c5-847d-4fb4-b85d-d1d2c801f77f">

### TRACEROUTE COMMAND
<img width="740" alt="Traceroute cmd" src="https://github.com/Ganesh23013987/4.Execution_of_NetworkCommends/assets/147473768/d689bf3e-8c86-4991-b7dd-258e6329d92b">

## Result
Thus Execution of Network commands Performed 
