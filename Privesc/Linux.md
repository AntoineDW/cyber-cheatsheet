# Linux privilege escalation methods

## Display the hostname of the machine
```bash
hostname
```

## Display informations about the kernel used by the machine
```bash
uname -a
```

## Display the version of the kernel used by the machine
```bash
cat /proc/version
```

## Display the running processes
```bash
ps aux
```

## Display the environment variables
```bash
env
```

## Display if user has some sudo privileges
```bash
sudo -l
```

## Display if SUID files exist
```bash
find / -perm -u=s -type f 2>/dev/null
```

## Display user capabilities
```bash
getcap -r / 2>/dev/null
```

## NFS privilege escalation
```bash
cat /etc/exports
```

Look for the `no_root_squash` configuration. If present, on local machine:

```bash
showmount -e [ip]
mount -o rw [ip]:[remote_folder] [local_folder]
```

Then create a SUID `/bin/bash` binary file.
