# Gcc

## Compile a C file
```bash
gcc [file] -o [outfile]
```

## Compile a C file without requiring dependencies
```bash
gcc -static [file] -o [outfile]
```

## Compile a C file without any protection
```bash
gcc [file] -o [outfile] -fno-stack-protector -z execstack -no-pie
```

## Compile a C file in 32-bits
```bash
gcc [file] -o [outfile] -m32
```
