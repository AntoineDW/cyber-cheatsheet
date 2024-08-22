# Mona

## Good example of how to use Mona to find bad characters
https://github.com/cris-m/Buffer-Overflow-Exploit-Development/blob/main/assets/documentations/characters.md

## Set the working directory
```bash
!mona config -set workingfolder C:\mona
```

## Generate bytearray for comparison
```bash
!mona bytearray -b "[badchars]"
```

## Compare the characters with the ones at the ESP address
```bash
!mona compare -f C:\mona\bytearray.bin -a [esp_address]
```

## Find all the possible JMP ESP
```bash
!mona jmp -r esp -cpb "[badchars]"
```
