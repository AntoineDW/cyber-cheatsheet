# Ffuf

A fast web fuzzer written in Go meaning "Fuzz Faster U Fool"

## Bruteforce a POST request
```bash
ffuf -X POST -w "[wordlist1]:W1" -w "[wordlist2]:W2" -d "username=W1&password=W2" -fr "Invalid credentials" -H "Content-Type: application/x-www-form-urlencoded" -u [url]
```

## Find all the possible endpoints of a REST API
```bash
ffuf -w [wordlist] -mc [valid_status_code] -u [url]/FUZZ
```
