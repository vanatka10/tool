# LDAP(389,636,3268,3268)
ldapsearch -x -H ldap://<IP> -D '' -w '' -b "DC=<1_SUBDOMAIN>,DC=<TLD>"
ldapsearch -x -H ldap://<IP> -D '<DOMAIN>\<username>' -w '<password>' -b "DC=<1_SUBDOMAIN>,DC=<TLD>"
//source:https://book.hacktricks.xyz/network-services-pentesting/pentesting-ldap//
# SMB(139,445)
smbclient
smbmap
//source:https://book.hacktricks.xyz/network-services-pentesting/pentesting-smb//
 bloodhound.py to collect and analyze all information about the Active Directory environment
//source:https://github.com/dirkjanm/BloodHound.py/tree/master/ //

