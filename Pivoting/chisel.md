# proxy
chisel1.exe client 10.10.16.3:9090 R:socks  
./chisel client 10.10.101.51:8001 R:1080:socks
# forward port
./chisel.exe client 10.10.16.17:8050 R:9090:127.0.0.1:9090
./chisel client 10.10.16.7:9090 R:3000:172.17.0.1:3000

# server
chisel server --reverse -p 9090
# use
## edit /etc/proxychains4.conf
## add sock5 127.0.0.1 1080
## proxychains4 <some command>
