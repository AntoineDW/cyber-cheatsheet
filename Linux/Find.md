# Find

Find is a tool used to search for files.

## Find SUID files in a system
```bash
find / -perm -u=s -type f 2>/dev/null
```

## Find files linked to a user
```bash
find / -user [user]
```

## Find files linked to a group
```bash
find / -group [group]
```

## Find file by its name
```bash
find / -type f -iname [name] -print 2>/dev/null
```
