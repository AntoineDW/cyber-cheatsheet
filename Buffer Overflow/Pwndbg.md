# Pwndbg

Pwndbg is a GDB plug-in that makes debugging with GDB suck less.

## Start debugging a binary with GDB
```bash
gdb
file [binary]
```

## List functions of a binary
```bash
info functions
```

## Disassemble a function of a binary
```bash
disassemble [function]
```

## Add a breakpoint at a specific address of a function
```bash
b *[address]
```

## Delete all the breakpoints
```bash
delete breakpoints
```

## Print memory during debug
```bash
x [register]
x [address]
```

## Modify memory during debug
```bash
set *[address] = [value]
```

## Create a cyclic pattern for memory research
```bash
cyclic [number_of_bytes]
```

## Search for a specific cyclic pattern
```bash
cyclic -l [pattern]
```

## Display the memory after the RSI register
```bash
x/200x $rsi
```

## Formats des payloads pour une éxécution de fonction
* 32-bits: padding + function + return + param1 + param2
* 64-bits: padding + pop rdi + param1 + pop rsi + param2 + function

## Format du payload pour une éxécution de shellcode
* 32-bits: padding + jmp esp + shellcode
* 32-bits: nop + shellcode + buffer address 
* 64-bits: nop + shellcode + nop + buffer address
