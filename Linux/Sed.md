# Sed

Sed is a command that can be used to read and adjust data streams.

## Remove blank lines from a file
```bash
sed -i '/^$/d' [file]
```

## Remove n first lines from a file
```bash
sed -i 1,[n]d [file]
```
