# SmbClient

SmbClient is a tool used to connect to SAMBA shares.

## Display public shares on the server
```bash
smbclient -L [ip] -U%
```

## Connect to a share
```bash
smbclient //[ip]/[share] -U[user]%[password]
```
