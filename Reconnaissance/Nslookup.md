# Nslookup

A tool to find IP addresses linked to a domain name.

## Find IP addresses linked to a domain
```bash
nslookup -type=[type] [domain]
```

The different types are:
* A:        IPv4 addresses
* AAAA:     IPv6 addresses
* CNAME:    Canonical name
* MX:       Mail servers
* SOA:      Start of authority
* TXT:      TXT records
