# Nmap

Nmap is a powerful network scanning tool.

## Scan all the possible ports
```bash
nmap -p- -oN [outfile] [ip]
```

## Scan specific ports in details
```bash
nmap -sC -sV -Pn -p[port1],[port2] -oN [outfile] [ip]
```

## Check the list of hosts that will be scanned
```bash
nmap -sL [ip]
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
