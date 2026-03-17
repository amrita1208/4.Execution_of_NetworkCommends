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

## Program:

## server:

```
import socket

dns_table = {
    "google.com": "142.250.190.78",
    "yahoo.com": "98.137.11.163",
    "openai.com": "104.18.12.123",
    "example.com": "93.184.216.34"
}

server_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

server_socket.bind(("127.0.0.1", 15353))

print("DNS Server running on port 5353...\n")

while True:
    message, client_address = server_socket.recvfrom(1024)
    domain = message.decode()
    print("Request received for:", domain)
    ip = dns_table.get(domain, "Domain not found")
    server_socket.sendto(ip.encode(), client_address)
```
## client:
```
import socket

client_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
server_address = ("127.0.0.1", 15353)

domain = input("Enter domain name: ")

# Send request to server
client_socket.sendto(domain.encode(), server_address)

ip_address, server = client_socket.recvfrom(1024)

print("IP Address:", ip_address.decode())

client_socket.close()
```
## Output

## server:
<img width="1547" height="929" alt="Screenshot 2026-03-17 141543" src="https://github.com/user-attachments/assets/fb4d0b15-1904-46c7-a8e8-f4e93c5f033d" />

## client:
<img width="1560" height="943" alt="Screenshot 2026-03-17 141559" src="https://github.com/user-attachments/assets/139aeff5-03c3-44e1-81ad-68c901078b53" />

## traceroute command:
<img width="841" height="335" alt="Screenshot 2026-03-17 142550" src="https://github.com/user-attachments/assets/6e309755-0b50-4778-b7d4-24c247914632" />

## Result
Thus Execution of Network commands Performed 
