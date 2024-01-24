# LDAP(389,636,3268,3268)
ldapsearch -x -H ldap://<IP> -D '' -w '' -b "DC=<1_SUBDOMAIN>,DC=<TLD>"  
ldapsearch -x -H ldap://<IP> -D '<DOMAIN>\<username>' -w '<password>' -b "DC=<1_SUBDOMAIN>,DC=<TLD>"  
//source:https://book.hacktricks.xyz/network-services-pentesting/pentesting-ldap//   
# SMB(139,445)
smbclient  
smbclient -U '%' -N \\\\<IP>\\<SHARE>    
enum4linux -a <MACHINE IP>   
sudo mount -t cifs -o username=cifs_share_user //10.10.11.222/Development /home/kali/Documents/Machines/HTB/Authority/mount/

crackmapexec smb 10.10.11.222 -u 'guest' -p '' --shares --rid-brute 10000 (dùng để hiển thị các smb share và --rid-brute 10000 để brute force username 1000)


smbmap 
//source:https://book.hacktricks.xyz/network-services-pentesting/pentesting-smb//   
 bloodhound.py to collect and analyze all information about the Active Directory environment   
//source:https://github.com/dirkjanm/BloodHound.py/tree/master/ //   

# SSH(22)
/brute force ssh/
hydra -l <USERNAME> -P /usr/share/wordlists/rockyou.txt ssh://10.10.61.213  
# gRPC(default 50051)
grpcui --plaintext IP:PORT   
grpcurl IP:PORT list  
grpcurl --plaintext IP:PORT list  
grpcurl -plaintext IP:PORT list something   
# MSSQL(1433)
impacket-mssqlclient -port 1433 DOMAIN/username:password@<target-ip>
impacket-mssqlclient -port 1433 DOMAIN/username:password@<target-ip> -windows-auth

bên trong mssql
EXEC xp_dirtree '{/path}'

xp_dirtree
 
# redis-cli (6379)
sudo apt install redis-tools  
redis-cli -h {target_IP}   
info  
get  
select  
key *  
# rdp (3389)
xfreerdp
xfreerdp /v:<IP> (default username of machine)
rdesktop -u <username> <IP>
rdesktop -d <domain> -u <username> -p <password> <IP>
xfreerdp [/d:domain] /u:<username> /p:<password> /v:<IP>
xfreerdp [/d:domain] /u:<username> /pth:<hash> /v:<IP> #Pass the hash

# 88 kerberos
https://github.com/ropnop/kerbrute
# upload 
https://github.com/flozz/p0wny-shell
