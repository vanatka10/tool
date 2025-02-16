# crack gitea pbkdf2$50000$50
sha256:<iterations>:<base64_salt>:<base64_hash>

format: hashpass:salt
```
cba20ccf927d3ad0567b68161732d3fbca098ce886bbc923b4062a3960d459c08d2dfc063b2406ac9207c980c47c5d017136:2d149e5fbd1b20cf31db3e3c6a28fc9b
e531d398946137baea70ed6a680a54385ecff131309c0bd8f225f284406b7cbc8efc5dbef30bf1682619263444ea594cfb56:8bf3e3452b78544f8bee9400d6936d34
               
```
```
awk -F: '{print "sha256:50000:" $2 ":" $1}' hash.txt | while IFS= read -r line; do
  salt=$(echo "$line" | cut -d: -f3 | base64 -w 0);
  hash=$(echo "$line" | cut -d: -f4 | base64 -w 0);
  echo "sha256:50000:$salt:$hash" >> hashformat.txt;
done
```
