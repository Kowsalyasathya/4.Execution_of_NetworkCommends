# EX4.Execution of NetworkCommands
## AIM :
Use of Network commands in Real Time environment
## Software : 
Command Prompt And Network Protocol Analyzer
## Procedure: 
To do this EXPERIMENT- follows these steps:
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

##  Program:
### PING COMMAND:
### CLIENT:
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
### SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### TRACEROUTE COMMAND:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
### PING COMMAND:
### CLIENT:
![318423663-e13ac1d1-e96b-41ae-b6fe-b95a747de3c8](https://github.com/Kowsalyasathya/4.Execution_of_NetworkCommends/assets/118671457/68f27e6f-8909-4555-a53a-21b9857feceb)
### SERVER:
![318423696-eccc570d-e5bd-47b8-adad-067c408cb650](https://github.com/Kowsalyasathya/4.Execution_of_NetworkCommends/assets/118671457/e3305f1e-1989-4ed0-879e-1eeb862dc706)
### TRACEROUTE COMMAND:
![318423711-e451f0ab-6927-4f8d-8de4-2ad928008669](https://github.com/Kowsalyasathya/4.Execution_of_NetworkCommends/assets/118671457/ec0d6430-8f64-4c18-ab6b-df761fc7123d)

## Result
Thus Execution of Network commands Performed 
