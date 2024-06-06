# Nmap

Nmap is a powerful network scanning tool.

## Usual scan
```bash
sudo nmap -sC -sV -O -oN [output_file] [ip]
```

## Scan using a proxy
```bash
sudo nmap -sC -sV -O 127.0.0.1 --proxy [proxy]
```

## Scan using proxychains
Modify /etc/proxychains4.conf by adding this line at the end:
`http [ip] [port]`

Then start a nmap scan
```bash
proxychains nmap -sC -sV -oN [output_file] [ip]
```
