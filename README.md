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

## CODE
CLIENT :
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
SERVER :
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode()) 
```
TRACER :
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans) 
```
## Output
TRACER :

![HEM CN EX7 IMG 1](https://github.com/hemreddy2005/4.Execution_of_NetworkCommends/assets/145633111/dcc2ca37-438f-410c-925a-f5cefe49c3ec)

CLIENT :

![HEM CN EX7 IMG 2](https://github.com/hemreddy2005/4.Execution_of_NetworkCommends/assets/145633111/9f2170c3-b3c3-4c55-8041-12346cedffc1)

SERVER :

![HEM CN EX7 IMG 3](https://github.com/hemreddy2005/4.Execution_of_NetworkCommends/assets/145633111/5025927c-2e88-4115-b763-5039ac9fae22)

## Result
Thus Execution of Network commands Performed 
