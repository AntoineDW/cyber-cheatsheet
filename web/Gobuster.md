# Gobuster

Gobuster is used to brute-force website directories.

## Find hidden pages in a website
```bash
gobuster dir -u [url] -w [wordlist]
```

## Specify valid and invalid status codes
```bash
gobuster dir -u [url] -w [wordlist] -s [valid_status_code] -b [invalid_status_code] dir
```
