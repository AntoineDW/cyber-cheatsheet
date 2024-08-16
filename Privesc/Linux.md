# Linux privilege escalation methods

## Display if user has some sudo privileges
```bash
sudo -l
```

## Display if SUID files exist
```bash
find / -perm -u=s -type f 2>/dev/null
```
