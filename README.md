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

## PROGRAM
## CLIENT.PY:
~~~
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

~~~
## SERVER.PY:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 ip=input("Enter the website you want to ping ")
 s.send(ip.encode())
 print(s.recv(1024).decode())
~~~

## Output
## PING COMMAND:
## CLIENT.PY:
![image](https://github.com/user-attachments/assets/3abf384e-71bd-49be-b359-f299f70c0d99)

## SERVER.PY:
![image](https://github.com/user-attachments/assets/003e9c10-d811-4944-9c46-75c54003b2b1)

## TRACEROUTE COMMMAND
![image](https://github.com/user-attachments/assets/d9c13ced-6f45-4bf5-b223-eaef998e9ccc)

## Result
Thus Execution of Network commands Performed 
