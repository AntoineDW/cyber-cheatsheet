# John

John is a tool used to crack password.

## Hash cracking
```bash
john --wordlist=[wordlist] --format=[format] [hash_file]
```

The list of john formats can be found here:
[John formats](https://pentestmonkey.net/cheat-sheet/john-the-ripper-hash-formats)

## /etc/passwd and /etc/shadow cracking
```bash
unshadow [passwd] [shadow] > [hash_file]
john --wordlist=[wordlist] --format=sha512crypt [hash_file]
```

## Single mode hash cracking
```bash
john --single --format=[format] [hash_file]
```

## ZIP file cracking
```bash
zip2john [zip_file] > [hash_file]
john --wordlist=[wordlist] [hash_file]
```
