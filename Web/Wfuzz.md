# Wfuzz

Wfuzz is a tool used to easily perform fuzzing research on websites.

## Find all the possible GET parameters of a REST API endpoint
```bash
wfuzz -c -w [wordlist] -sc [valid_status_code] [url]?FUZZ=test
```

## Find all the possible endpoints of a REST API
```bash
wfuzz -c -w [wordlist] -sc [valid_status_code] [url]/FUZZ
```
