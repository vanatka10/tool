# LDAP(389,636,3268,3268)
ldapsearch -x -H ldap://<IP> -D '' -w '' -b "DC=<1_SUBDOMAIN>,DC=<TLD>"  
ldapsearch -x -H ldap://<IP> -D '<DOMAIN>\<username>' -w '<password>' -b "DC=<1_SUBDOMAIN>,DC=<TLD>"  
//source:https://book.hacktricks.xyz/network-services-pentesting/pentesting-ldap//   
# SMB(139,445)
smbclient
smbclient -U '%' -N \\\\<IP>\\<SHARE>  
enum4linux -a <MACHINE IP> 
sudo mount -t cifs -o username=cifs_share_user //10.10.11.222/Development /home/kali/Documents/Machines/HTB/Authority/mount/

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
